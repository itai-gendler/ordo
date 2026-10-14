---
appliesTo:
- type: capability
  id: delete-tag
- type: capability
  id: remove-tag-from-bookmark
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/tags.service.ts#TagsService
- kind: code
  role: implementation
  target: apps/mobile/src/components/tags/TagActionsSheet.tsx
---

# Deleting a tag keeps the bookmarks that carried it

Deleting a tag or taking it off a bookmark never deletes a bookmark.
