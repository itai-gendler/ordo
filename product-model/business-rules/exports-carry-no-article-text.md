---
appliesTo:
- type: capability
  id: export-library
  contexts:
  - {place: 'ordo-app::signed-in::data'}
references:
- kind: code
  role: implementation
  target: apps/server/src/import-export/export.service.ts#ExportService
---

# An export carries bookmark details, never article text

Exports hold links, titles, descriptions, authors, dates, folders, tags and reading state.
