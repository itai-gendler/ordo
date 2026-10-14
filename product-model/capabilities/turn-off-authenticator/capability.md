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
  target: apps/mobile/app/(app)/settings/security.tsx
---

# Turn off authenticator

An Account holder removes the authenticator from their account, which also discards their backup codes.
