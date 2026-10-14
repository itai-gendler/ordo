---
domain: library
availability:
- {place: 'ordo-app::signed-in'}
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/bookmarks.service.ts#BookmarksService
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/(tabs)/index.tsx
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/folder/[id].tsx
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/tags/[id].tsx
- kind: code
  role: implementation
  target: apps/mobile/src/components/bookmarks/SearchFilterMenu.tsx
---

# Browse library

An Account holder looks through their library: folders and unfiled bookmarks on the home list, a folder's bookmarks, the bookmarks under one tag, and search across everything with filters.
