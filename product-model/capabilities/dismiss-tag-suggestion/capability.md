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

# Dismiss suggested tag

An Account holder dismisses a tag the Product suggested for a bookmark; it is not suggested for that bookmark again.
