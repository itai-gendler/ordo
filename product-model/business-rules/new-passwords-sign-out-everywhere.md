---
appliesTo:
- type: capability
  id: change-password
- type: capability
  id: reset-password
references:
- kind: code
  role: implementation
  target: apps/server/src/auth/auth.service.ts#AuthService
---

# A new password signs the account out everywhere

Changing the password ends every session and starts a new one for the device that changed it; resetting it ends every session.
