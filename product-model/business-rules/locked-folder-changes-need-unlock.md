---
appliesTo:
- type: capability
  id: save-bookmark
- type: capability
  id: move-bookmark
- type: capability
  id: rename-folder
- type: capability
  id: delete-folder
- type: capability
  id: lock-folder
- type: capability
  id: import-bookmarks
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/folder-access.service.ts#FolderAccessService
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/folders.service.ts#FoldersService
---

# Changing a locked folder or what is in it needs the folder unlocked

Saving into, moving into or out of, renaming, re-locking, deleting or importing into a locked folder works only while the folder is unlocked on the device.
