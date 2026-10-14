---
domain: account
availability:
- {place: 'ordo-app::signed-in'}
references:
- kind: code
  role: implementation
  target: apps/server/src/auth/avatar.service.ts#AvatarService
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/settings/account.tsx
---

# Change profile picture

An Account holder chooses or takes a photo for their account.
