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
  target: apps/mobile/app/(app)/settings/index.tsx
---

# Sign out

An Account holder signs this device out from Settings.
