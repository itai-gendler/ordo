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
  target: apps/mobile/src/components/bookmarks/CreateFolderPanel.tsx
---

# Create folder

An Account holder creates a folder with a name and an icon.
