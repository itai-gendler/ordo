---
entities:
- {entity: folder, shows: [Name, Bookmark count, Lock type]}
- {entity: import, shows: [File name, Format, New bookmarks, Already saved, Skipped rows, New folders, Locked folders, Imported, Updated, Failed rows, Problem], collects: [Duplicate handling, All at once]}
references:
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/settings/data.tsx
- kind: code
  role: implementation
  target: apps/mobile/src/components/settings/ImportFlow.tsx
---

# Data

Importing bookmarks from a file and exporting the library or chosen folders.
