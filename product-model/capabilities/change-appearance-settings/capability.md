---
domain: preferences
availability:
- {place: 'ordo-app::signed-in'}
references:
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/settings/appearance.tsx
- kind: code
  role: implementation
  target: apps/mobile/src/store/settings.ts#useSettingsStore
---

# Change appearance settings

An Account holder sets how the app looks and moves on this device: design, theme, colors and motion.
