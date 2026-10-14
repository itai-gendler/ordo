---
entities:
- {entity: account, shows: [Authenticator], collects: [Backup codes]}
references:
- kind: code
  role: implementation
  target: apps/mobile/app/(auth)/mfa.tsx
---

# Sign-in code

The second sign-in step for an account with an authenticator: an authenticator code, a backup code or an emailed code.
