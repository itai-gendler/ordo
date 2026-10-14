---
appliesTo:
- type: entity
  id: account
  effect: removes
permits:
- related:
  - {verb: has, entity: account-holder}
- related:
  - {verb: has, entity: server-owner}
- unattended: true
references:
- kind: code
  role: implementation
  target: apps/server/src/auth/auth.service.ts#AuthService
---

# Only the person signed in to an account deletes it

An account is deleted only from that account, or by the Product when an unconfirmed sign-up expires.
