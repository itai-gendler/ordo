---
entities:
- {entity: tag, shows: [Name, Color]}
- {entity: bookmark, shows: [Title, Site, Description, Tags, Read, Reminder, Reading time, Content kind]}
references:
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/tags/[id].tsx
---

# Tag

The bookmarks carrying one tag.
