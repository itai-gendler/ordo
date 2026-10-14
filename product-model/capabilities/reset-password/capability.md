---
domain: account
availability:
- {place: 'ordo-app::signed-out'}
references:
- kind: code
  role: implementation
  target: apps/server/src/auth/auth.service.ts#AuthService
- kind: code
  role: implementation
  target: apps/mobile/app/(auth)/forgot-password.tsx
- kind: code
  role: implementation
  target: apps/mobile/app/(auth)/reset-password.tsx
---

# Reset password

A Visitor who forgot their password asks for a reset code by email, then enters it with a new password. Every device signed in to the account is signed out.
