---
entities:
- {entity: server, shows: [Name, Version]}
- {entity: device-settings, shows: [Server address]}
references:
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/settings/server.tsx
---

# Hosting

The server the app talks to, its status and version, and the ways to change server or rename it.
