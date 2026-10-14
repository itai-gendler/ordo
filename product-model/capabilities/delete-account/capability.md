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
  target: apps/mobile/app/(app)/settings/delete-account.tsx
---

# Delete account

An Account holder deletes their account and everything in it: folders, bookmarks, tags, highlights and sessions.
