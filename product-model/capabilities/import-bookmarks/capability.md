---
domain: data
availability:
- {place: 'ordo-app::signed-in'}
references:
- kind: code
  role: implementation
  target: apps/server/src/import-export/import.service.ts#ImportService
- kind: code
  role: implementation
  target: packages/shared/src/schemas/import-export.ts
- kind: code
  role: implementation
  target: apps/mobile/src/components/settings/ImportFlow.tsx
---

# Import bookmarks

An Account holder imports bookmarks from an ordo export, a browser's bookmarks file or a CSV file. The Product reads the file and shows what it will do; the Account holder decides how links already saved are handled and confirms.
