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
  target: apps/mobile/src/components/tags/CreateTagPanel.tsx
- kind: code
  role: implementation
  target: packages/shared/src/schemas/tag.ts#CreateTagSchema
---

# Create tag

An Account holder creates a tag with a name and a color.
