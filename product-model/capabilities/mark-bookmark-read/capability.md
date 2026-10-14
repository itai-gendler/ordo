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
  target: apps/mobile/src/components/bookmarks/BookmarkActionsSheet.tsx
---

# Mark as read

An Account holder marks one bookmark, a selection, or everything in a folder or in the unfiled list as read.
