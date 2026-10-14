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
  target: apps/mobile/app/(app)/settings/email.tsx
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/settings/verify-email.tsx
---

# Change email

An Account holder changes the email on their account. The Product emails a code to the new address and a notice to the current one, and the change takes effect once the code is entered.
