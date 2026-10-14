---
appliesTo:
- type: entity
  id: highlight
  effect: creates
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
  target: apps/server/src/bookmarks/highlights.service.ts#HighlightsService
---

# Only the account that owns a bookmark highlights its highlights

Highlights belong to the bookmark's account; only that account highlights them.
