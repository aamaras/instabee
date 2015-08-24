# instabee

A script that will:

Get credentials:
- ask for your instapaper credentials and a goal name
- ask for your beeminder credentials
- get and store your oauth key for each

Check for new unread items and update beeminder:
- get a list of unread bookmarks, excluding those already received
- add any new unread bookmarks to the beeminder goal
- store those unread bookmarks in the list so they don't get retrieved again next time

Check for new read items and update beeminder:
- get a list of read bookmarks, excluding those already receieved
- subtract any read bookmarks from the beeminder goal
- store those read bookmarks in the list so they don't get retrieved again next time

Check for new deleted items and update beeminder:
- as above

Check the sums add up:
- get the unread count from beeminder
- sum the unreads from instapaper
- do something if they don't match (set the beeminder figure to zero and redo everything based on the current instapaper list?)