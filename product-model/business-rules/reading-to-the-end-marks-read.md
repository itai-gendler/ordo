---
appliesTo:
- type: capability
  id: read-bookmark
- type: capability
  id: mark-bookmark-read
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/bookmarks.service.ts#BookmarksService
- kind: code
  role: implementation
  target: packages/shared/src/constants.ts#READ_COMPLETION_THRESHOLD
---

# A bookmark read to the end of its article is marked read

Reaching 98% of an article marks the bookmark read and records when.
