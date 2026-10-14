---
entities:
- {entity: account, shows: [Authenticator, Backup codes]}
references:
- kind: code
  role: implementation
  target: apps/mobile/src/components/auth/MfaEnrollmentScreen.tsx
---

# Protect your account

Shown in place of the library while the server requires an authenticator the account does not have yet.
