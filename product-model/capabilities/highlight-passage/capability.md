---
availability:
- {place: 'ordo-app::signed-in'}
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/highlights.service.ts#HighlightsService
- kind: code
  role: implementation
  target: packages/shared/src/highlights.ts
- kind: code
  role: implementation
  target: apps/mobile/src/components/reader/ReaderPane.tsx
---

# Highlight passage

An Account holder selects text in an article and highlights it. A highlight that touches existing ones joins them into one.
