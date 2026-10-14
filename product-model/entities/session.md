---
references:
- kind: code
  role: implementation
  target: apps/server/src/auth/session.service.ts#SessionService
---

# Session

One device signed in to an account.

## Information kept

- **Device name** — the device that signed in
- **Device type** — the kind of device
- **Signed in at** — when the session started
- **Last active** — when the device last used the session
- **This device** — whether the session is the one the person is using now
