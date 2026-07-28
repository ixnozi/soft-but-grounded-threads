# Threads Posts Repo

This repo holds ONLY the daily Threads post content for @ixnozi's Soft But Grounded automation. It's read by a scheduled cloud agent that posts a daily approval message to Slack, and (on your ✅ reaction) schedules the 5 posts to Buffer.

## Structure

```
Week of [Month Day, Year]/
  Monday.txt
  Tuesday.txt
  Wednesday.txt
  Thursday.txt
  Friday.txt
  Saturday.txt
  Sunday.txt
```

The week folder name must match the Monday of that week, in the format `Week of July 27, 2026` (same convention as the main "Soft But Grounded — Week of [Date]" folder on your Desktop, minus the "Soft But Grounded — " prefix).

## Daily file format

Each day file contains exactly 5 posts, in order (mapped to fixed posting times: 8:00am, 11:00am, 1:00pm, 4:00pm, 7:00pm SAST), separated by a line containing only `---`:

```
[Post 1 text]
---
[Post 2 text]
---
[Post 3 text]
---
[Post 4 text]
---
[Post 5 text]
```

## IMPORTANT — you must push after every edit

The cloud agent only ever sees what's on GitHub. Whenever you create or edit a day's file (including after reacting ✏️ in Slack to request an edit), you must run:

```
git add -A && git commit -m "update posts" && git push
```

from inside this folder before the next scheduled check — otherwise the automation will act on stale content.
