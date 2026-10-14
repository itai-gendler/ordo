---
domain: account
availability:
- {place: 'ordo-app::signed-out'}
references:
- kind: code
  role: implementation
  target: apps/server/src/auth/auth.service.ts#AuthService
- kind: code
  role: implementation
  target: apps/server/src/auth/mfa.service.ts#MfaService
- kind: code
  role: implementation
  target: apps/mobile/app/(auth)/login.tsx
- kind: code
  role: implementation
  target: apps/mobile/app/(auth)/mfa.tsx
---

# Sign in

A Visitor signs in with their email and password. When the account has an authenticator, sign-in continues with an authenticator code, a backup code or a code sent by email before the device gets a session.
