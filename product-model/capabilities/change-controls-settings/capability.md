---
domain: preferences
availability:
- {place: 'ordo-app::signed-in'}
references:
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/settings/controls.tsx
- kind: code
  role: implementation
  target: apps/mobile/src/store/settings.ts#useSettingsStore
---

# Change controls settings

An Account holder sets what the create button does, how shared links are saved, and where websites open, on this device.
