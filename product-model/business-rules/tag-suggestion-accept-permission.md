---
appliesTo:
- type: entity
  id: tag-suggestion
  effect: removes
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

# Only the account that owns a bookmark accepts its suggested tags

Accepting a suggestion puts the tag on the bookmark and drops the suggestion; only the bookmark's account does it. A suggestion changes nothing until it is accepted.
