---
appliesTo:
- type: capability
  id: sign-in
- type: capability
  id: create-account
references:
- kind: code
  role: implementation
  target: apps/server/src/auth/session.service.ts#SessionService
- kind: code
  role: implementation
  target: packages/shared/src/constants.ts#SESSION
---

# An account stays signed in on at most 10 devices

Signing in on another device ends the session the account used least recently, and a session unused for 14 days ends.
