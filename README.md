# instabee

A script that will track your [instapaper](http://instapaper.com) queue using [beeminder](http://beeminder.com). 

May track either the size of your backlog (ie you want your reading to keep pace with your article adding) or the number of articles you read each week (ie you want to read a certain number each week, but don't care if the backlog grows exponentially - maybe you add too many articles). But I'm starting with the backlog and may never bother with the read rate option.

Get credentials:

- ask for your instapaper credentials
- ask for your beeminder credentials and a goal name
- get and store your oauth key for each
- ask whether you want to track 'articles read per week' or 'size of instapaper backlog'
	- if 'articles read per week', goal should be 'do more'
	- if 'size of instapaper backlog', goal should be 'do less' (or whittle down?)

Check for new read items and update beeminder:

- get a list of read bookmarks, excluding those already receieved
- if tracking 'articles read per week':
	- add any read bookmarks to the beeminder goal
- if tracking 'size of instapaper backlog':
	- subtract any read bookmarks from the beeminder goal
- store those read bookmarks in the list so they don't get retrieved again next time

Check for new deleted items and update beeminder:

- as for read items

Check for new unread items and update beeminder:

- if tracking 'size of instapaper backlog':
	- get a list of unread bookmarks, excluding those already received
	- add any new unread bookmarks to the beeminder goal
	- store those unread bookmarks in the list so they don't get retrieved again next time

Check the sums add up:

- if tracking 'size of instapaper backlog':
	- get the unread count from beeminder
	- sum the unreads from instapaper
	- do something if they don't match (reset the beeminder figure to zero and redo everything based on the current instapaper list?)
