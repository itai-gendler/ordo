---
type: mobile-app
actors:
- visitor
- account-holder
- server-owner
references:
- kind: code
  role: implementation
  target: apps/mobile/app/_layout.tsx
- kind: code
  role: implementation
  target: packages/shared/src/contract.ts
- kind: doc
  role: intent
  target: README.md
---

# ordo app

The Android app, downloaded from the project's releases. It talks to one ordo server at a time, ordo Cloud unless the person
points it at a server they run, and accepts links shared to it from other apps.
