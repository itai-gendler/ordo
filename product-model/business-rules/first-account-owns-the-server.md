---
appliesTo:
- type: entity
  id: server
  effect: changes
  facts: [Owner, Has accounts]
permits:
- actors:
  - visitor
  when:
  - {fact: Has accounts, is: 'No'}
references:
- kind: code
  role: implementation
  target: apps/server/src/server/instance-admin.ts#claimInstanceOwner
- kind: code
  role: implementation
  target: apps/server/src/server/instance-admin.ts#userCanRenameInstance
---

# The first account to be created becomes the server's owner

Only the creation of a server's first account records an owner. Where the operator configured an owner email, the account with that email is the owner instead, and only the owner renames the server.
