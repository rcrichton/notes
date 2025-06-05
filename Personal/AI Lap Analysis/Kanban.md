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
- [ ] Chat message loading - again!


## Up Next

- [ ] Login button redirects?
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

- [ ] When session is added to a user through sharing, the chat doesn't load with the new priveledges


## Done

**Complete**
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