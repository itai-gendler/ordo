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
  target: apps/server/src/bookmarks/folder-token.service.ts#FolderTokenService
- kind: code
  role: implementation
  target: packages/shared/src/schemas/folder.ts#SetFolderPasswordSchema
- kind: code
  role: implementation
  target: apps/mobile/src/components/bookmarks/FolderActionsSheet.tsx
- kind: code
  role: implementation
  target: apps/mobile/src/lib/device-folder-lock.ts
---

# Lock folder

An Account holder locks a folder with a password, a PIN, a pattern or the device lock. A locked folder's bookmarks stay hidden until it is unlocked.
