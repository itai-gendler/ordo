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
- kind: code
  role: implementation
  target: apps/mobile/src/lib/open-website.ts
- kind: code
  role: implementation
  target: apps/mobile/src/lib/bookmark-reminders.ts#reminderClearsOnOpen
---

# Read bookmark

An Account holder opens a bookmark: an article opens in ordo's reader with its highlights, and a website opens in a browser. Reading progress is saved as they go.
