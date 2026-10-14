---
domain: data
availability:
- {place: 'ordo-app::signed-in'}
references:
- kind: code
  role: implementation
  target: apps/server/src/import-export/export.service.ts#ExportService
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/settings/data.tsx
---

# Export library

An Account holder exports their bookmarks as an ordo JSON file, a browser bookmarks HTML file or a CSV file, for the whole library or chosen folders.
