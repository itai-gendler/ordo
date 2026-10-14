---
appliesTo:
- type: capability
  id: sign-in
- type: capability
  id: verify-email
- type: capability
  id: create-account
references:
- kind: code
  role: implementation
  target: apps/server/src/auth/auth.service.ts#AuthService
- kind: code
  role: implementation
  target: apps/server/src/auth/auth.guard.ts#AuthGuard
---

# Where the server requires email verification, an account is used only after its email is verified

On such a server an unverified account cannot sign in, and a signed-in device whose account is not verified can do nothing else.
