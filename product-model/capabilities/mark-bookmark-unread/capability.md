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

# Mark as unread

An Account holder marks a read bookmark, or a selection, as unread.
