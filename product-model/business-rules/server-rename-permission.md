---
appliesTo:
- type: entity
  id: server
  effect: changes
  facts: [Name]
permits:
- actors:
  - server-owner
  when:
  - {fact: Renaming allowed, is: 'Yes'}
references:
- kind: code
  role: implementation
  target: apps/server/src/server/instance-admin.ts#userCanRenameInstance
- kind: code
  role: implementation
  target: apps/server/src/server/server.service.ts#ServerService
---

# Only the server owner renames the server, while renaming is allowed

The server's name is changed only by its owner, and not at all where the operator turned renaming off (as ordo Cloud does).
