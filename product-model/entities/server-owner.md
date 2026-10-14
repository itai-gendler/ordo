---
kind: person
acts: external
relations:
- entity: account
  verb: has
  cardinality: one-to-one
references:
- kind: code
  role: implementation
  target: apps/server/src/server/instance-admin.ts#claimInstanceOwner
---

# Server owner

The account holder who owns the server: its first account, or the account with the owner email the operator configured. Besides keeping a library, the owner names the server.
