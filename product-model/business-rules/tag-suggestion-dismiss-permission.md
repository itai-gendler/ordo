---
appliesTo:
- type: entity
  id: tag-suggestion
  effect: changes
  to: Dismissed
permits:
- related:
  - {verb: has, entity: bookmark}
  - {verb: owns, entity: account}
  - {verb: has, entity: account-holder}
- related:
  - {verb: has, entity: bookmark}
  - {verb: owns, entity: account}
  - {verb: has, entity: server-owner}
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/bookmarks.service.ts#BookmarksService
---

# Only the account that owns a bookmark dismisses its suggested tags

A suggestion is turned down only by the account the bookmark belongs to; it changes nothing on the bookmark.
