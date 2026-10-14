---
domain: library
availability:
- {place: 'ordo-app::signed-in'}
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/bookmarks.service.ts#BookmarksService
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/tag-suggestion.service.ts#TagSuggestionService
---

# Accept suggested tag

An Account holder accepts one of the tags the Product suggested for a bookmark.
