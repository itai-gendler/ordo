---
availability:
- {place: 'ordo-app::signed-in'}
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/bookmarks.service.ts#BookmarksService
- kind: code
  role: implementation
  target: apps/mobile/src/components/reader/ReaderPane.tsx
---

# Mark as website

An Account holder tells the Product a bookmark is a website rather than an article, so it opens in a browser.
