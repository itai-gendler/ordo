---
domain: hosting
availability:
- {place: 'ordo-app::signed-in'}
references:
- kind: code
  role: implementation
  target: apps/server/src/server/server.service.ts#ServerService
- kind: code
  role: implementation
  target: apps/server/src/server/instance-admin.ts#userCanRenameInstance
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/settings/server.tsx
---

# Rename server

The Server owner gives the server the name the app shows to everyone who uses it.
