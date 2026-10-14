---
appliesTo:
- type: entity
  id: account
  effect: changes
  facts: [Display name, Profile picture, New email, Email, Authenticator, Reader text size, Reader typeface, Reader line spacing, Reader theme, Reader AMOLED black]
permits:
- related:
  - {verb: has, entity: account-holder}
- related:
  - {verb: has, entity: server-owner}
references:
- kind: code
  role: implementation
  target: apps/server/src/auth/auth.service.ts#AuthService
---

# Only the person signed in to an account changes its details

An account's name, picture, email, authenticator and reader settings are changed only from that account.
