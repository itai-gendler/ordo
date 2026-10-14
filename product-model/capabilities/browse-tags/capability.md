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
  target: apps/mobile/app/(app)/tags/index.tsx
---

# Browse tags

An Account holder sees all their tags with how many bookmarks carry each.
