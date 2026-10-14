---
entities:
- {entity: account, shows: [Email], collects: [New email, Password]}
references:
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/settings/email.tsx
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/settings/verify-email.tsx
---

# Email

Where the Account holder asks to change their email and confirms the new one with its code.
