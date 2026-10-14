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
  target: apps/server/src/auth/registration-open.ts#isRegistrationOpen
- kind: code
  role: implementation
  target: apps/mobile/app/(auth)/register.tsx
---

# Create account

A Visitor creates an account on the server the app is connected to, with a display name, email and password. When the server requires email verification, the new account waits for the emailed code before anyone can sign in to it.
