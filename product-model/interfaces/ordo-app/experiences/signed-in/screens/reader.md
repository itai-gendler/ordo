---
entities:
- {entity: bookmark, shows: [Title, Site, Author, Published on, Reading time, Article, Reading progress, Reminder, Tags, Content kind]}
- {entity: highlight, shows: [Passage]}
- {entity: account, collects: [Reader text size, Reader typeface, Reader line spacing, Reader theme, Reader AMOLED black]}
references:
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/reader/[id].tsx
- kind: code
  role: implementation
  target: apps/mobile/src/components/reader/ReaderPane.tsx
---

# Reader

One bookmark open: its article with highlights and reader controls, or its website.
