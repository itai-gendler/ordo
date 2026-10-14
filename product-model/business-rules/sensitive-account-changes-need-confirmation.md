---
appliesTo:
- type: capability
  id: change-email
- type: capability
  id: change-password
- type: capability
  id: delete-account
- type: capability
  id: turn-off-authenticator
- type: capability
  id: create-backup-codes
references:
- kind: code
  role: implementation
  target: apps/server/src/auth/auth.service.ts#AuthService
- kind: code
  role: implementation
  target: apps/server/src/auth/mfa.service.ts#MfaService
---

# Changing the email or password, or deleting the account, needs the current password and the second step

These changes need the current password and, while an authenticator is set up, an authenticator or backup code. Turning the authenticator off and creating new backup codes need an authenticator or backup code.
