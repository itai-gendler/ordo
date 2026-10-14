---
availability:
- {place: 'ordo-app::signed-in'}
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/bookmarks.service.ts#BookmarksService
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/extraction.service.ts#ExtractionService
- kind: code
  role: implementation
  target: apps/mobile/src/components/reader/ReaderPane.tsx
---

# Mark as article

An Account holder tells the Product a bookmark kept as a website is an article; the Product fetches it again as an article.
