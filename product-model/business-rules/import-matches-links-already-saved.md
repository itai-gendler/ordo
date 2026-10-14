---
appliesTo:
- type: capability
  id: import-bookmarks
  contexts:
  - {place: 'ordo-app::signed-in::data'}
references:
- kind: code
  role: implementation
  target: packages/shared/src/schemas/import-export.ts#normalizeUrlForMatch
- kind: code
  role: implementation
  target: apps/server/src/import-export/import.service.ts#ImportService
---

# An import treats a link as already saved when it matches one in the library

Links match after ignoring letter case in the scheme and host, default ports, a trailing slash on the root and an empty fragment. Skip leaves saved links alone, Update refreshes them, and Add copies saves them again; repeats within the file import once unless copies are added. With All at once, the import saves everything or nothing.
