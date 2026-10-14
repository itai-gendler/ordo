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
---

# Rename folder

An Account holder renames a folder.
