---
domain: tags
availability:
- {place: 'ordo-app::signed-in'}
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/tags.service.ts#TagsService
- kind: code
  role: implementation
  target: apps/mobile/src/components/tags/TagActionsSheet.tsx
---

# Delete tag

An Account holder deletes a tag; the bookmarks that carried it are kept.
