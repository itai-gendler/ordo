---
appliesTo:
- type: capability
  id: create-account
- type: capability
  id: verify-email
references:
- kind: code
  role: implementation
  target: apps/server/src/auth/auth.service.ts#AuthService
---

# An account left unconfirmed is removed when its code expires

An account waiting for email verification is removed once its latest code has expired; asking for a new code starts another 10 minutes.
