---
appliesTo:
- type: capability
  id: browse-library
- type: capability
  id: read-bookmark
- type: capability
  id: browse-tags
- type: capability
  id: export-library
- type: capability
  id: unlock-folder
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/folder-access.service.ts#FolderAccessService
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/folder-token.service.ts#FolderTokenService
- kind: code
  role: implementation
  target: packages/shared/src/constants.ts#TOKEN_TTL
---

# A locked folder's bookmarks stay hidden until it is unlocked on the device

While a folder is locked, its bookmarks, their highlights and their counts stay out of the folder, the library, search, tag counts, reminders and whole-library exports, until the folder is unlocked on that device. An unlock lasts 10 minutes, and changing or removing the lock ends every current unlock.
