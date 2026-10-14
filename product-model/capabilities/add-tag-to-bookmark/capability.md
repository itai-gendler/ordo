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
  target: apps/mobile/src/components/tags/EditTagsSheet.tsx
---

# Add tag to bookmark

An Account holder puts one or more of their tags on a bookmark, or on several selected bookmarks at once.
