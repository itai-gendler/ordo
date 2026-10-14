---
domain: account
availability:
- {place: 'ordo-app::signed-in'}
references:
- kind: code
  role: implementation
  target: apps/server/src/auth/avatar.service.ts#AvatarService
---

# Remove profile picture

An Account holder removes the picture from their account.
