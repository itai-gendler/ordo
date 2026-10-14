---
domain: library
availability:
- {place: 'ordo-app::signed-in'}
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/folders.service.ts#FoldersService
- kind: code
  role: implementation
  target: apps/mobile/src/components/bookmarks/FolderActionsSheet.tsx
- kind: code
  role: implementation
  target: apps/mobile/src/lib/undoable-delete.ts
---

# Delete folder

An Account holder deletes a folder together with every bookmark in it, with a few seconds to undo.
