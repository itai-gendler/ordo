---
appliesTo:
- type: capability
  id: create-tag
- type: capability
  id: edit-tag
references:
- kind: code
  role: implementation
  target: packages/shared/src/schemas/tag.ts#tagNameKey
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/tags.service.ts#TagsService
---

# Tag names are unique within an account, whatever the capitalization

Two tags of one account never share a name once letter case and repeated spaces are ignored.
