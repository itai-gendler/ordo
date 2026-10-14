---
appliesTo:
- type: entity
  id: folder
  effect: reads
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

# Only the account that owns a folder reads it

A folder belongs to one account's library. Only that account, signed in, reads it.
