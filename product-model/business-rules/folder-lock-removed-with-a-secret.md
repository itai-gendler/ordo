---
appliesTo:
- type: capability
  id: remove-folder-lock
  contexts:
  - {place: 'ordo-app::signed-in::library'}
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/folders.service.ts#FoldersService
- kind: code
  role: implementation
  target: packages/shared/src/schemas/folder.ts#RemoveFolderPasswordSchema
---

# A folder's lock comes off only with its secret or the account password

Removing a lock needs the folder's password, PIN or pattern, the device lock it was set with, or the account password.
