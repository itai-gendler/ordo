---
appliesTo:
- type: capability
  id: delete-bookmark
- type: capability
  id: delete-folder
- type: capability
  id: delete-tag
references:
- kind: code
  role: implementation
  target: apps/mobile/src/lib/undoable-delete.ts
---

# Deleting bookmarks, folders and tags can be undone for a few seconds

After a deletion is confirmed, the app offers Undo for about five seconds before anything is deleted on the server.
