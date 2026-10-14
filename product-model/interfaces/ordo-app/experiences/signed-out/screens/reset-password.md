---
entities:
- {entity: account, collects: [Email, Password]}
references:
- kind: code
  role: implementation
  target: apps/mobile/app/(auth)/forgot-password.tsx
- kind: code
  role: implementation
  target: apps/mobile/app/(auth)/reset-password.tsx
---

# Reset your password

Where a Visitor asks for a reset code and chooses a new password with it.
