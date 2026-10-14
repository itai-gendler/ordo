---
domain: active-sessions
availability:
- {place: 'ordo-app::signed-in'}
references:
- kind: code
  role: implementation
  target: apps/server/src/auth/session.service.ts#SessionService
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/settings/sessions.tsx
---

# Revoke session

An Account holder signs one of their other devices out.
