---
appliesTo:
- type: capability
  id: switch-server
  contexts:
  - {place: 'ordo-app::signed-in::hosting'}
  - {place: 'ordo-app::signed-out::sign-in'}
references:
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/settings/server.tsx
- kind: doc
  role: intent
  target: README.md
---

# Switching servers copies nothing

Each server keeps its own accounts and libraries. Switching the app to another server signs the device out and leaves the library on the server it was saved to.
