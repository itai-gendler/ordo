---
domain: library
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
  target: apps/server/src/bookmarks/reader.service.ts#ReaderService
- kind: code
  role: implementation
  target: apps/mobile/src/components/bookmarks/AddBookmarkSheet.tsx
- kind: code
  role: implementation
  target: apps/mobile/src/components/IncomingShareHandler.tsx
---

# Save bookmark

An Account holder saves a link to their library, optionally into a folder and with tags. The Product saves it at once, then fetches the page in the background and keeps a readable article when there is one, or keeps the link as a website.
