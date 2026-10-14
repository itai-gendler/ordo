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
  target: apps/mobile/src/components/bookmarks/MoveSheet.tsx
---

# Move to folder

An Account holder moves a bookmark, or a selection of bookmarks, into a folder or out to the unfiled list.
