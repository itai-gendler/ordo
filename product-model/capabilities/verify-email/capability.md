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
  target: apps/mobile/app/(auth)/verify-email.tsx
---

# Verify email

A Visitor confirms the email of an account waiting for verification by entering the 6-digit code the Product emailed. The account becomes active and the Visitor is sent to sign in.
