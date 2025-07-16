---

kanban-plugin: board

---

## Backlog

- [ ] Scrub from charts? Floating playback bar?
- [ ] Session history stats
- [ ] Chat push notifications
- [ ] Pricing - checkout flow doesn't seem to work on first signup
- [ ] Feature: sync up youtube video
- [ ] Mini sectors viz
- [ ] Optimal time compare
- [ ] Chat message loading - again! - remove initial functionality, rather do properly?
- [ ] See that a session is a shared session - title?
- [ ] Email coming from perfect apex not supabase?
- [ ] App bar slow to collapse
- [ ] Time codes didn't correlate in AI chat - see https://discord.com/channels/712415168348553349/714382956957007922/1380106633916583966
- [ ] Profile pic rerenders when toggling between chats and when chat renders e.g. streaming
- [ ] Login from history page lost shared session
- [ ] Likes for session or laps
- [ ] Feature: Activity feed, profile, follow list
- [ ] Feature: achievements
- [ ] Feature: Automatic posts to socials for achievements and new sessions


## Up Next

- [ ] When session is not added to user, chat cannot be viewed
- [ ] Global touch up for launch
- [ ] Add ToS
- [ ] Product launch - reddit, product hunt?, HN?


## In Progress

- [ ] Check data displays and interpolation - implement smoothing
- [ ] Add support for phase 1 data import formats
	
	- [x] Track addict
	- [ ] RaceChrono
	- [ ] VBO


## Done

**Complete**
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
{"kanban-plugin":"board","list-collapse":[false,false,false,false]}
```
%%