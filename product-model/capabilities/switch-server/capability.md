---
domain: hosting
availability:
- {place: 'ordo-app::signed-out'}
- {place: 'ordo-app::signed-in'}
references:
- kind: code
  role: implementation
  target: apps/mobile/src/components/settings/SelfHostFlow.tsx
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/settings/server.tsx
- kind: code
  role: implementation
  target: apps/mobile/src/lib/hosting.ts#CLOUD_SERVER_URL
- kind: code
  role: implementation
  target: apps/mobile/src/components/auth/ServerConnectSheet.tsx
---

# Switch server

A person points the app at a different ordo server: ordo Cloud, or a server they run themselves. Switching while signed in signs the device out, and libraries stay on the server they were saved to.
