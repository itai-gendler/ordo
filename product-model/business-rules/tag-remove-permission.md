---
appliesTo:
- type: entity
  id: tag
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
  target: apps/server/src/bookmarks/tags.service.ts#TagsService
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/tags.controller.ts
---

# Only the account that owns a tag deletes it

A tag belongs to one account's library. Only that account, signed in, deletes it.
