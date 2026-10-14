---
domain: security
availability:
- {place: 'ordo-app::signed-in'}
references:
- kind: code
  role: implementation
  target: apps/server/src/auth/mfa.service.ts#MfaService
- kind: code
  role: implementation
  target: apps/mobile/src/components/auth/MfaSetupPanel.tsx
- kind: code
  role: implementation
  target: apps/mobile/src/components/auth/MfaEnrollmentScreen.tsx
- kind: code
  role: implementation
  target: apps/server/src/auth/auth.guard.ts#AuthGuard
---

# Set up authenticator

An Account holder adds an authenticator app as a second sign-in step and receives ten backup codes. On a server that requires an authenticator, an account without one is sent here before it can do anything else.
