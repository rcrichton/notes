---

kanban-plugin: board

---

## Backlog

- [ ] Notification center
	* chat messages
	* what's new
	* later follower activity
- [ ] Auto event detection
- [ ] User profile
- [ ] Upload multiple sessions at once
- [ ] Feat: User garage
- [ ] Device support: AIM + MOTECH
- [ ] Support GM Cosworth PDR
	
	See https://mail.google.com/mail/u/1/#inbox/FMfcgzQcqlGxBRKfKbNGmltbSqgMlQCM
- [ ] Compare top laps across all sessions at a track
	
	Useful for autocross too
	How to get AI Analysis for this?
	Track session type
	How is it different to session compare?
- [ ] Feature: event viz in track map
- [ ] Marketing: track map viz
	
	- [ ] Create short video ad
	- [ ] Create screenshots
	- [ ] Reddit post
	- [ ] Instagram post
	- [ ] Email to users
	- [ ] Boost post
- [ ] Feature: Activity feed, profile, follow list
	
	Likes for session or laps
	
	Chat push notifications
	
	User garage: 1. Add 'My Vehicle(s)' section to the left-side menu and allow the user to add their vehicle(s), including make, model etc, but also allow them to list their modifications and things like that, so public session info is more insightful, plus it allows people to brag a little, and upload photos. Also allow users to select what gear they're using (e.g. RaceChrono, Vbox, Dragy etc). If users have multiple vehicles, allow them to easily select one when adding a session - if they only have 1 vehicle, have it selected by default when adding a new session. Could also allow the driver name to be set here as well.
- [ ] #Marteking How to get faster reel - a worked example
- [ ] Revenue: sponsorship - logo in session list linking to site
- [ ] Revenue: Ads in the feed about new devices or apps or performance parts
- [ ] #Feature Sync up youtube video
- [ ] Mini sectors viz
- [ ] Optimal time compare
- [ ] Fix: App bar slow to collapse
- [ ] Feature: achievements
- [ ] Feature: Automatic posts to socials for achievements and new sessions
- [ ] Import F1 data via https://tracinginsights.com/data/
- [ ] Feature: implement tracking of vehicle OBD data for visualisation
- [ ] Feature: AI chat/insights in compare
- [ ] Finish support for generic VBO. issue is they are non-standard.
	- RaceChrono VBO - [laptiming] (long, lat, flip long) - inline first point on start finish second point for orientation?
	- RaceBox VBO - [laptiming] (lat, long; flip long) - points make finish line
	- TrackAddict VBO, no [laptiming] but has lap column
- [ ] Feature: Video sync e.g. using https://www.mux.com/pricing/video
- [ ] Feature: 3rd party integration to popular lap timers
- [ ] Analyse specific corners?
	
	"And then when analyzing, if on the playback map, you could say, hey I want to look at this specific corner and then the map/data timeline would jump to the start of that corner and the data would also auto shift the x axis/time to sync up all the laps so you can see how each lap varies through that single corner."
	
	"The sectional analysis is what is useful, but I still look for my best lap time, though I'm not going to slow anyone else down to get it."
- [ ] The upload modal disappears if you click outside it and any entered data is removed.
- [ ] Social: Create discord?
- [ ] **Account for traffic or slow laps**
	
	"The most significant piece of feedback on the AI is that it doesn't seem to account for traffic or other external factors. One user pointed out that the AI flagged a massive speed difference in a corner that was clearly caused by traffic, not driver error."
	
	"One thing I would like to know, in hpde timing, is how many times in a lap I slowed down to let a faster driver by. Maybe throttle lifts in a straight would be an approximate measure."
- [ ] Allow 2 letter Names - nickname
- [ ] Email in export data
- [ ] Refactor: move server action to proper API
- [ ] Bug: While retriggering Ai insights for large session: Request body exceeded 10MB for /session/6c244849-84c8-4119-bd1c-841a80260778. Only the first 10MB will be available unless configured. See https://nextjs.org/docs/app/api-reference/config/next-config-js/middlewareClientMaxBodySize for more details.
	 ⨯ [Error: Body exceeded 4mb limit.
	To configure the body size limit for Server Actions, see: https://nextjs.org/docs/app/api-reference/next-config-js/serverActions#bodysizelimit] {
	  statusCode: 413,
	  digest: '3065771895'
	}
	 POST /session/6c244849-84c8-4119-bd1c-841a80260778 500 in 615ms
- [ ] Split leaderboard to a separate page
- [ ] User customizable dashboard
- [ ] Allow map to be rotated?
- [ ] GPS fine global adjustments


## Up Next

- [ ] User dashboard
	
	* Profile pic
	* Bio
	* Stats
	* Latest sessions
	* Cars
- [ ] Better support for motocycles
	
	In vehicle list
	Lean angle
	Let AI know it's a bike


## In Progress

- [ ] Revenue: Build affiliate program feature
	- [x] Build tracking
	- [ ] Email partners
- [ ] Test point to point support for trackaddict and racebox


## Done

**Complete**
- [x] Click on charts to seek
- [x] What happened when signed out with AI prompts on charts - Already sorted, hidden
- [x] Use one single GCP for the app - move maps API - enable free tier for development
- [x] Support autocross data
	- [x] Fix import
	- [x] Add to AI context
	- [x] Copy changes (even in AI context)
	- [x] Social story
- [x] Prompts not working on dev
	
	Also add feature flag
- [x] AI prompts on analysis cards
- [x] Feat: share session stats card to socials
- [x] PA home link
- [x] Confirm link copy - animation
- [x] Fix: Map tile loading faster or cache
- [x] Annual pricing
- [x] Marketing: Create post ad
- [x] Marketing: release delta, stats and inconsistency zones
	
	- [x] Create screenshots
	- [x] Reddit post
	- [x] Instagram post
	- [x] Email to users
	
	Due: @{2025-11-03}
- [x] Inconsistency zones
	 - [x] Make pro feature?
	 - [x] Don't show if very consistent
	 - [x] Performance test
	 - [x] Add to AI context
	 - [x] Check if AI uses smoothed data
- [x] Device support: Harry's laptimer
- [x] Device support: CircuitStorm
- [x] Feat: Add notes
- [x] Feat: edit session
- [x] Fix: Pre-fetching responsiveness
- [x] Add basic sponsor feature
- [x] Device support: Apex Pro Gen 1
- [x] Enhance SEO
- [x] Session history stats
- [x] First 2 session uploaded should get free AI analysis
- [x] keep the screen alive while the play back of the lap is running on the map. If it's a PWA you can use await navigator.wakeLock.request('screen').
- [x] **Fix use of units in AI analysis**
	
	A user reported that their preference for MPH in the settings is ignored, with the app displaying KPH instead.
- [x] **Remember car details**
	
	The app doesn't remember the user's car and driver name, requiring them to be re-entered with each use.
- [x] Beta launch - reddit
- [x] Handle  GPS delay?
- [x] Add compare feature to landing page
- [x] Fix playback playing too slow
- [x] Allow users to compare their own sessions for free
- [x] Make map playback smoother
- [x] Auto detect accel channels and direction
- [x] Only owner should see details analysis button
- [x] Fix file import issues
- [x] Beta launch - email
- [x] Set public feature flags
- [x] Configure live payment gateway
- [x] Comprehensive testing
- [x] Shared chat @AI not creating time tag links
- [x] Change time tag to select lap rather than deselect all
- [x] Change rate limits to monthly
- [x] Check payment flow
	- [x] Pricing - checkout flow doesn't seem to work on first signup
	- [x] Cancelling deactivates subscription
	- [x] Failed payment deactivates subscription
- [x] Chat stays loading for logged out users
- [x] Edit and update landing page info and screenshots
- [x] Time codes didn't correlate in AI chat - see https://discord.com/channels/712415168348553349/714382956957007922/1380106633916583966
- [x] Chat times and dates
- [x] Investigate wrong AI insights numbers
	
	The issue is the AI works on raw data not smoothed.
- [x] Can't save session
- [x] Security check
- [x] Email coming from perfect apex not supabase?
- [x] Configure emails SMTP
- [x] Data processing
	- [x] Finalise processing and interpolation
	- [x] Calculated lap boundary?
	- [x] Parser validation
- [x] Laps aren't deleted when session is removed in db (cascade)
- [x] Restrict AI insights to subs
- [x] When redirecting after upload, plan usage won't load. This prevent uploading another file as storage check doesn't work.
- [x] Open up discover page to all
- [x] Restrict compare feature to subs
- [x] Compare selection should only be the same track and layout
- [x] Track layout required
- [x] Add support for phase 1 data import formats
	
	- [x] Track addict
	- [x] RaceChrono
	- [x] Race box CSV
	- [x] Lap Legend CSV
- [x] Toggling smoothing doesn't keep zoom the same
- [x] Toolbar disappears once no laps are selected - error
- [x] Collect test data file from community
- [x] AI could be wrong message
- [x] In discover plan styling in wrong for my account - probably duplicate sub
- [x] Scrub from charts? Floating playback bar? Replace mobile toolbar?
	- [x] Basic design and playback functionality
	- [x] Hook up chat features
- [x] Google auth
	- [x] Check new user signup
- [x] Save session not working. Free user. 
	
	{
	    "code": "42P17",
	    "details": null,
	    "hint": null,
	    "message": "infinite recursion detected in policy for relation \"user_sessions\""
	}
- [x] Go to app button on pricing page
- [x] - [x] Ensure users can only have one active subscription
- [x] - [x] Chart tooltips
- [x] - [x] Tooltip consistency
- [x] - [x] Ability to switch plans
- [x] Fix compare session selection (pagination)
- [x] Fix for you section in discover
- [x] - [x] History and discover pagination
- [x] - [x] Message send animation or inject message in chat before saved
- [x] Chat message loading - again! - remove initial functionality, rather do properly?
- [x] - [x] Faster loading, better loading state
- [x] - [x] Sessions timestamp not only date
- [x] - [x] AI time tagging
- [x] - [x] File upload first then metadata
- [x] - [x] Note about each upload format
- [x] - [x] AI Insights error handling
- [x] - [x] Distance toggle unit preferences support
- [x] - [x] Lap events support for units
- [x] - [x] Remove mapbox map
- [x] - [x] Delta legend
- [x] - [x] Improve lap selector styling
- [x] Improve display of under construction mobile toolbar buttons
- [x] Add ToS
- [x] When session is not added to user, chat cannot be viewed
- [x] Check data displays and interpolation - implement smoothing
- [x] Sending lap context for AI from client is not efficient
- [x] When session is uplaoded, data on screen doesn't react/relaod
- [x] AI chat should sync when a new message arrives
- [x] PRO avatar border
- [x] Change all user references to use username, consistent avatars, pro and racer badges
- [x] Set reference lap (compare with shared and self)
- [x] Change units
- [x] Auto AI Insights - panel and chat
- [x] Toolbar to add session to saved sessions
- [x] Implement plan limits
	
	- [x] Upload limit
	- [x] AI rate limit
- [x] Mobile toolbar
- [x] User profile schema
- [x] Optimise storage of telemetry points
	
	See [[Storage optimization plan]]
- [x] Session discovery
- [x] Draw racing lines
- [x] Reddit post with demo shared session
- [x] Try google maps for map
- [x] Enhance community vibes for landing page
- [x] Login button redirects?
- [x] Go to app button for landing page
- [x] When session is added to a user through sharing, the chat doesn't load with the new priveledges
- [x] Remove email blocking
- [x] Check login flow
- [x] Set Gemini billing and limit
- [x] Disable uploads
- [x] Add lap context to @AI
- [x] Fix track map frame rate
- [x] Refresh landing page
- [x] Session chat
	
	* [x] basic chat
	- [x] time tagging
	- [x] Invoke AI in group chat
- [x] Session sharing
- [x] Session history needs to be responsive
- [x] Get good LLM answers, data pre-processing
- [x] Track map should follow points
- [x] Fix lap number to graph map mis-match - off by one
- [x] Fix lap calcualtion
- [x] Add/fix interpolation of data when uploaded
- [x] Fix waitlist styling based on suggestions [here](https://discord.com/channels/712415168348553349/714382956957007922/1354706690121007114)
- [x] **Subscription management**
	- [x] Manage subscription page
	- [x] Payment gateway integration
	- [x] Pricing page
- [x] User signup and login
- [x] Waiting list page
- [x] Move session analysis off project root




%% kanban:settings
```
{"kanban-plugin":"board","list-collapse":[false,false,false,false],"tag-colors":[]}
```
%%