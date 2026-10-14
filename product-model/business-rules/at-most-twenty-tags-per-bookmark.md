---
appliesTo:
- type: capability
  id: add-tag-to-bookmark
- type: capability
  id: accept-tag-suggestion
- type: capability
  id: save-bookmark
- type: capability
  id: import-bookmarks
references:
- kind: code
  role: implementation
  target: packages/shared/src/constants.ts#MAX_TAGS_PER_BOOKMARK
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/bookmarks.service.ts#BookmarksService
---

# A bookmark carries at most 20 tags

Adding tags to several bookmarks at once skips the bookmarks that are full.
