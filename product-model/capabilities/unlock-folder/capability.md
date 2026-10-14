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
  target: apps/mobile/src/components/bookmarks/LockPrompt.tsx
- kind: code
  role: implementation
  target: apps/mobile/src/store/folder-tokens.ts
---

# Unlock folder

An Account holder opens a locked folder on this device with its password, PIN, pattern or the device lock. The folder stays open on this device for 10 minutes.
