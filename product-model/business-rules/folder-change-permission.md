---
appliesTo:
- type: entity
  id: folder
  effect: changes
permits:
- related:
  - {verb: owns, entity: account}
  - {verb: has, entity: account-holder}
- related:
  - {verb: owns, entity: account}
  - {verb: has, entity: server-owner}
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/folder-access.service.ts#FolderAccessService
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/folders.service.ts#FoldersService
---

# Only the account that owns a folder changes it

A folder belongs to one account's library. Only that account, signed in, changes it.
