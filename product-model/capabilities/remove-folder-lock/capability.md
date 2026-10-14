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
  target: packages/shared/src/schemas/folder.ts#RemoveFolderPasswordSchema
- kind: code
  role: implementation
  target: apps/mobile/src/components/bookmarks/FolderActionsSheet.tsx
---

# Remove lock

An Account holder removes a folder's lock with the folder's secret or, when that is not at hand, with their account password.
