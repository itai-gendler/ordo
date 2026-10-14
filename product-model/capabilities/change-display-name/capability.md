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
  target: apps/mobile/app/(app)/settings/display-name.tsx
---

# Change display name

An Account holder changes the name shown on their account.
