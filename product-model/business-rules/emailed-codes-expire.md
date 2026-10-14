---
appliesTo:
- type: capability
  id: verify-email
- type: capability
  id: reset-password
- type: capability
  id: change-email
- type: capability
  id: sign-in
references:
- kind: code
  role: implementation
  target: packages/shared/src/constants.ts#EMAIL_OTP
- kind: code
  role: implementation
  target: apps/server/src/auth/auth.service.ts#AuthService
---

# Emailed codes work for 10 minutes and allow 5 wrong tries

Codes for confirming an email, changing it, resetting a password and signing in by email have 6 digits, expire after 10 minutes, stop working after 5 wrong tries, and are replaced by any newer code of the same kind.
