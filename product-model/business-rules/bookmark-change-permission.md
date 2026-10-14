---
appliesTo:
- type: entity
  id: bookmark
  effect: changes
permits:
- related:
  - {verb: owns, entity: account}
  - {verb: has, entity: account-holder}
- related:
  - {verb: owns, entity: account}
  - {verb: has, entity: server-owner}
- unattended: true
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/folder-access.service.ts#FolderAccessService
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/bookmarks.service.ts#BookmarksService
---

# Only the account that owns a bookmark changes it

A bookmark belongs to one account's library. Only that account, signed in, changes it; the Product's own background fetching and reminders act on it for that account.
