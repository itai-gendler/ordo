---
availability:
- {place: 'ordo-app::signed-in'}
references:
- kind: code
  role: implementation
  target: apps/server/src/auth/auth.service.ts#AuthService
- kind: code
  role: implementation
  target: apps/mobile/src/components/reader/ReaderControlsSheet.tsx
- kind: code
  role: implementation
  target: packages/shared/src/schemas/reader.ts#ReaderPreferencesSchema
---

# Change reader settings

An Account holder sets how articles read: text size, typeface, line spacing and theme. The settings belong to the account, so every device signed in to it reads the same way.
