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
  target: apps/mobile/src/lib/undoable-delete.ts
---

# Delete bookmark

An Account holder deletes a bookmark, or a selection, with a few seconds to undo.
