---
availability:
- {place: 'ordo-app::signed-in'}
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/highlights.service.ts#HighlightsService
- kind: code
  role: implementation
  target: apps/mobile/src/components/reader/ReaderPane.tsx
---

# Remove highlight

An Account holder removes a highlight, or only part of one by selecting the text to unhighlight.
