---
actors:
- account-holder
- server-owner
access: authenticated
references:
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/_layout.tsx
- kind: code
  role: implementation
  target: apps/server/src/auth/auth.guard.ts#AuthGuard
---

# Signed in

Where a signed-in person keeps their library: saving, reading, filing, tagging and highlighting bookmarks, and their account,
security, hosting and data settings.
