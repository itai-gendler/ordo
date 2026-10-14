---
appliesTo:
- type: capability
  id: delete-folder
  contexts:
  - {place: 'ordo-app::signed-in::library'}
references:
- kind: code
  role: implementation
  target: apps/server/prisma/schema.prisma
- kind: code
  role: implementation
  target: apps/mobile/src/components/bookmarks/FolderActionsSheet.tsx
---

# Deleting a folder deletes every bookmark in it

A folder's bookmarks go with it; they are not moved to the unfiled list.
