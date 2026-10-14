---
entities:
- {entity: account, collects: [Display name, Email, Password]}
references:
- kind: code
  role: implementation
  target: apps/mobile/app/(auth)/register.tsx
---

# Create account

Where a Visitor creates an account on the current server.
