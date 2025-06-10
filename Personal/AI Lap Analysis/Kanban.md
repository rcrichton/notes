---

kanban-plugin: board

---

## Backlog

- [ ] Set reference lap (compare with shared and self)
- [ ] Chat push notifications
- [ ] Pricing - checkout flow doesn't seem to work on first signup
- [ ] When session is uplaoded, data on screen doesn't react/relaod
- [ ] Loading latest session might leak session IDs, only list owner sessions
- [ ] Feature: sync up youtube video
- [ ] ">" 50 users won't load chat participants correctly
- [ ] Change units
- [ ] Sending lap context for AI from client is not efficient
- [ ] Mini sectors viz
- [ ] PRO avatar border
- [ ] Chat message loading - again! - remove initial functionality, rather do properly?
- [ ] See that a session is a shared session - title?
- [ ] Email coming from perfect apex not supabase?
- [ ] App bar slow to collapse
- [ ] Time codes didn't correlate in AI chat - see https://discord.com/channels/712415168348553349/714382956957007922/1380106633916583966
- [ ] Profile pic rerenders when toggling between chats and when chat renders e.g. streaming
- [ ] Login from history page lost shared session
- [ ] Scrub from charts?
- [ ] Draw racing lines
- [ ] Likes for session or laps


## Up Next

- [ ] Reddit post with demo shared session
- [ ] Optimise storage of telemetry points
	
	See [[Storage optimization plan]]
- [ ] Implement plan limits
	
	- [ ] Upload limit
	- [ ] AI rate limit
- [ ] Add support for phase 1 data import formats
	
	- [ ] Track addict
	- [ ] RaceChrono
- [ ] Check data displays and interpolation
- [ ] Global touch up for launch
- [ ] Product launch - reddit, product hunt?, HN?


## In Progress



## Done

**Complete**
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