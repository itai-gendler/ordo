---
appliesTo:
- type: capability
  id: set-up-authenticator
- type: capability
  id: sign-in
references:
- kind: code
  role: implementation
  target: apps/server/src/auth/auth.guard.ts#AuthGuard
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/_layout.tsx
---

# Where the server requires an authenticator, an account without one can only set one up

On such a server, a signed-in account without an authenticator sees Protect your account and can do nothing else until it sets one up.
