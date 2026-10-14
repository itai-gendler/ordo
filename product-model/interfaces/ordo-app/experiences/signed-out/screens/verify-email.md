---
entities:
- {entity: account, collects: [Email]}
references:
- kind: code
  role: implementation
  target: apps/mobile/app/(auth)/verify-email.tsx
---

# Verify your email

Where a Visitor enters the code emailed for a new account.
