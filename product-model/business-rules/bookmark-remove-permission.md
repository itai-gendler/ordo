---
appliesTo:
- type: entity
  id: bookmark
  effect: removes
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
  target: apps/server/src/bookmarks/bookmarks.service.ts#BookmarksService
---

# Only the account that owns a bookmark deletes it

A bookmark belongs to one account's library. Only that account, signed in, deletes it.
