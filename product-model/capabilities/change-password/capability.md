---
domain: account
availability:
- {place: 'ordo-app::signed-in'}
references:
- kind: code
  role: implementation
  target: apps/server/src/auth/auth.service.ts#AuthService
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/settings/password.tsx
---

# Change password

An Account holder changes their password with their current one. Every device is signed out and this one starts a fresh session.
