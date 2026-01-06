## Scope
Text-only documentation of the generic post-parse processing pipeline that turns raw parsed telemetry into per-lap, uniformly sampled series with lap-level stats. Entry point from server action: `process-lap-data.ts`.

## Pipelines & Config
*   **Target Sample Rate**: 10Hz (0.1s interval).
*   **Coordinate System**: WGS84 (Lat/Lon).
*   **Distance**: Geodesic calculation (via `geolib` and `@turf/distance`).
*   **Interpolation Strategy**:
    *   **GPS (< 5Hz)**: Cubic Spline (`cubic-spline` library) for smooth trajectory.
    *   **GPS (>= 5Hz)**: Linear interpolation (sufficient for high-rate GNSS).
    *   **Accelerometer**: Mean-window resampling (averages points within the 0.1s bucket to reduce noise).

## Inputs & Parsing
Input is a source specific file (CSV, VBO, etc) processed by a specific parser from `app/lib/parsers/`.

### Verified Parsers
| Format / Source | Implementation | Status |
| :--- | :--- | :--- |
| **TrackAddict** | `trackaddict.ts` | Production |
| **RaceChrono** | `racechrono-csv.ts` | Production |
| **RaceBox** | `racebox-csv.ts` | Production |
| **VBOX / Generic** | `vbo-generic.ts` | Production |
| **Lap Legend** | `lap-legend-csv.ts` | Production |
| **Harry's Lap Timer**| `harrys-lap-timer.ts`| Experimental |
| **Apex Pro** | `apex-pro.ts` | Experimental |
| **Circuit Storm** | `circuit-storm.ts` | Experimental |

**Output of Parser**: 
- `RawDataPoint[]`: Flat array of points (`time`, `lat`, `lon`, `speed`, `accel_x/y/z`, `lap_number` if available).
- `Metadata`: Candidate `start_finish_lat/lon`, `track_name`, `driver`, etc.

## Generic Processing Steps (`process-lap-data.ts`)

1.  **Group by Lap**
    *   Iterate through raw points.
    *   Bin them into `Map<LapNumber, RawDataPoint[]>`.
    *   *Self-healing*: If timestamps are out of order (common in some exports), sort them by time.

2.  **Refine Lap Boundaries (Crossing Detection)**
    *   **Goal**: Precision start/finish timing is crucial for delta-t comparison.
    *   **Synthetic Line**: If no specific S/F line is in metadata, we calculate the "synthetic" start/finish line by detecting the geographic seam where Lap N ends and Lap N+1 begins (using `geolib` to find the closest points between laps).
    *   **Crossing Point**: We use `@turf/line-intersect` to find the exact sub-millisecond point where the vehicle trajectory intersects the S/F line. 
    *   **Correction**: We inject an interpolated point at exactly `distance = 0` (or `distance = track_length`) to ensure perfect graph alignment.

3.  **Discard Incomplete Laps**
    *   **Out-lap**: Lap 1 is typically discarded (cold tires, standing start).
    *   **In-lap**: The final lap is discarded *unless* it is the only lap.
    *   **Short Laps**: Laps < 2 points or < 0.5s duration are pruned as artifacts.

4.  **Compute Cumulative Distance**
    *   Traverse each lap's sorted points.
    *   Calculate geodesic distance between `Point[i]` and `Point[i-1]`.
    *   Accumulate `totalDistance`. This becomes the X-axis for "Distance" mode charts.

5.  **Interpolate to Uniform Grid (10Hz)**
    *   Create a target time arrays: `[0.0, 0.1, 0.2, ... lapDuration]`.
    *   **Spline Interpolation**: For GPS coordinates, generate cubic splines (`x` vs `time`, `y` vs `time`) to sample smooth lat/lon at each target time.
    *   **Compression**: This step effectively regularizes the data, making storage consistent (Gzipped JSON arrays of equal length for same-duration laps).

6.  **Stats & Serialization**
    *   Compute `maxSpeed`, `avgSpeed`, `sectorTimes` (if sectors defined).
    *   Package results into `LapData` objects.
    *   Return to `upload-lap-data.ts` for Gzipping and storage.
