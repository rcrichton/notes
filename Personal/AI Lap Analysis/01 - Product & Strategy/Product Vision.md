**Core Belief**: Driving mastery should be accessible to every enthusiast, not just those with professional race engineers.

**Mission**: To build the world's most intelligent, proactive AI race engineer that empowers drivers to master their craft by freeing their data, fostering community learning, and providing actionable, personalized coaching.

## Key Pillars
1.  **AI-First Coaching**: Move beyond passive charts to active guidance. The AI acts as a proactive race engineer that analyses your driving DNA to reveal *unseen* opportunities. It automates the expertise of a professional coach, teaching you specific techniques to go faster without you needing to ask the right questions.
2.  **Free & Open Data**: Driving data belongs to the driver, not the device. We exist to break down proprietary silos, creating a universal platform where data from any source—real world or sim—can be analyzed, compared, and understood in one unified place.
3.  **Community & Shared Mastery**: Knowledge accelerates when it is shared. We are building the global library of driving data, where every lap driven contributes to the collective intelligence of the community, helping every enthusiast learn from the experience of others.

> [!NOTE]
> For a detailed list of currently implemented capabilities, see [[Feature Index]].

## Tech Stack
- **Web app**: Next.js 15 (App Router), React 19, Tailwind CSS v4
- **UI Components**: shadcn/ui, Radix UI, Recharts, Framer Motion
- **Maps**: Mapbox GL JS, Google Maps API
- **Backend/DB**: Supabase (PostgreSQL, Auth, Storage, Realtime)
- **AI**: Google Gemini Pro (via `@google/genai` and Vercel AI SDK)
- **Data Processing**: Custom Typescript pipeline (cubic-spline, turf.js, geolib)
- **Hosting**: Vercel

---

## Competitive Context
**Direct Competitors:**
- [MyRaceLab](https://myracelab.com/)
- [Garmin Catalyst](https://youtu.be/9nDkfLvMTfM?si=9I0k0jV0u2dLAaUh)
- [VBOX](https://vboxmotorsport.co.uk/)
- [RaceCue](https://racecue.com/)
- [Serious Racing](https://serious-racing.com/)
- [Circuit Tools](https://www.vboxmotorsport.co.uk/index.php/en/customer-area/software)
- [Fire Laps](https://firelaps.com/)
- [XRace.ai](https://app.xrace.ai/home)
- [Telemetry Copilot](https://www.laminarinsights.com/project/telemetry-copilot)
- [MoveDot.ai](https://www.movedot.ai/)
- [VPR](https://www.vpr.com/)
- [ApexHero](https://apexhero.app/)

**Sim-focused:**
- [Traophi.ai](https://www.youtube.com/watch?v=ePNMmoBRGbU) (Moving to real world)
