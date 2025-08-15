### Scope
Text-only documentation of the generic post-parse processing pipeline that turns raw parsed telemetry into per-lap, uniformly sampled series with lap-level stats. Entry point: `processLapData`.

### Inputs from parsers
- `rawDataPoints`: Array of `RawDataPoint` with fields: `time`, `lap`, `speed`, `latitude`, `longitude`, `accel_x`, `accel_y`, `accel_z`, `gps_updated`, optional `heading`, optional `absoluteTimestamp`.
- `metadata`: May include `markerLines` (notably a `START_FINISH` line), `sessionStartTime`, `trackName`, and original headers.
- Parsers set `gps_updated` to indicate points where GPS was updated; this drives boundary refinement, distance calculation, and spline construction.

### Generic processing steps
- Group by lap
  - Build a `Map<lapNumber, RawDataPoint[]>`, inserting each point by its `lap`.
  - Ensure each lap’s points are time-sorted; sort when out-of-order is detected.

- Refine lap boundaries (if `START_FINISH` marker exists)
  - For each transition between adjacent laps:
    - Pick the last GPS-updated point of the previous lap and the first GPS-updated point of the current lap.
    - Compute the precise crossing with the `START_FINISH` line via line intersection; interpolate time, speed, and accel values along the segment based on distance ratio.
    - Insert this crossing as the end of the previous lap and the start of the current lap.
  - Skips refinement when the line is missing, when either side lacks GPS-updated points, or for single-lap data.

- Discard incomplete laps
  - Remove lap 0 (pre-start accumulation).
  - Remove the original last lap number (commonly incomplete) only if doing so leaves at least one other lap; otherwise keep it.

- Compute cumulative distance per lap
  - Traverse each lap’s time-sorted points.
  - Increment cumulative distance only at `gps_updated === 1` points using precise geodesic distance from the last GPS-updated point.
  - Attach the cumulative distance to every point (including non-GPS-updated ones) to produce a distance-bearing series.

- Interpolate to a uniform time grid
  - Grid: from 0 to the lap’s duration at 0.1s intervals; always include the exact end time.
  - Time normalization: the output time axis is per-lap, starting at 0.
  - Accelerometer channels (`accel_x`, `accel_y`, `accel_z`):
    - Mean-resampled per grid window; if a window has no points, fall back to linear interpolation between surrounding raw points, then to nearest-point if needed.
  - GPS channels (latitude, longitude, speed, distance):
    - If the lap has at least two GPS-updated points:
      - Downsample GPS points if the average GPS interval is too fine relative to the grid to reduce spline instability.
      - Remove duplicate time values before spline creation.
      - Build cubic splines for each channel and evaluate at each grid time; clamp evaluation times to the spline’s domain.
      - Per-sample fallback: nearest GPS point if a spline evaluation fails.
      - Full fallback: linear interpolation between surrounding GPS points if spline creation fails.
    - If fewer than two GPS-updated points, use linear interpolation over all points.
  - Result: a per-lap array of uniformly sampled points with time, distance, speed, lat/long, and accelerometer values.

- Compute per-lap stats and assemble results
  - Lap time: last raw time minus first raw time (after any boundary refinement).
  - Max/avg speed: computed from the raw points in the lap (robust to NaN/Infinity).
  - Skip laps with fewer than two points or non-positive duration.
  - Output per lap: `lapTime`, `points` (the interpolated series), `maxSpeed`, `avgSpeed`.

### Output shape
- Returns a `Map` keyed by lap number with:
  - `lapTime`: seconds
  - `points`: uniformly sampled series at 0.1s resolution, time-normalized from 0 to lap duration
  - `maxSpeed`, `avgSpeed`
- Also returns original `metadata` from the parser for upstream use (e.g., `sessionStartTime`, track name).

### Key behaviors and safeguards
- Boundary refinement is conservative: requires a `START_FINISH` line and GPS-updated points on both sides of a lap transition.
- Incomplete laps are pruned (lap 0 and original last lap), but never prune away the only remaining lap.
- Distance is geodesic, accumulated only between GPS-updated points; every point inherits the running total.
- Interpolation emphasizes stability:
  - Cubic splines with de-duplication, clamping, and per-sample failure fallback.
  - Downsampling high-rate GPS data before spline creation to avoid overfitting and numeric issues.
  - Mean-window resampling for accelerometers to align to the time grid, with fallback interpolation.
- Time series are normalized to a per-lap 0-based axis for consistent charting and comparisons.

Status update: Wrote concise, text-only documentation of the generic processing pipeline after parsing, focusing on the steps, data flows, and fallback behaviors. No code included.

- Documented grouping, boundary refinement with `START_FINISH`, incomplete-lap pruning, geodesic distance accumulation, 0.1s resampling, accel mean-resample, GPS spline + fallbacks, and final lap stats/output.
- Called out normalization, conditions that trigger fallbacks, and safeguards that prevent empty/invalid laps from being emitted.