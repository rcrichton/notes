---

kanban-plugin: board

---

## Backlog

- [ ] Session history stats
- [ ] Chat push notifications
- [ ] Feature: sync up youtube video
- [ ] Mini sectors viz
- [ ] Optimal time compare
- [ ] App bar slow to collapse
- [ ] Likes for session or laps
- [ ] Feature: Activity feed, profile, follow list
- [ ] Feature: achievements
- [ ] Feature: Automatic posts to socials for achievements and new sessions
- [ ] Consistency score
- [ ] Import F1 data via https://tracinginsights.com/data/
- [ ] Feature: implement tracking of vehicle OBD data for visualisation
- [ ] Feature: event viz in track map
- [ ] Feature: AI chat/insights in compare
- [ ] Finish support for generic VBO. issue is they are non-standard.
	- RaceChrono VBO - [laptiming] (long, lat, flip long) - inline first point on start finish second point for orientation?
	- RaceBox VBO - [laptiming] (lat, long; flip long) - points make finish line
	- TrackAddict VBO, no [laptiming] but has lap column
- [ ] Handle  GPS delay?
- [ ] Feature: Generate session card for sharing


## Up Next

- [ ] Beta launch - reddit


## In Progress



## Done

**Complete**
- [x] Only owner should see details analysis button
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