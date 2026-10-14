---
domain: security
availability:
- {place: 'ordo-app::signed-in'}
references:
- kind: code
  role: implementation
  target: apps/server/src/auth/mfa.service.ts#MfaService
- kind: code
  role: implementation
  target: apps/mobile/src/components/auth/BackupCodesDialog.tsx
---

# Create new backup codes

An Account holder replaces their backup codes with ten new ones.
