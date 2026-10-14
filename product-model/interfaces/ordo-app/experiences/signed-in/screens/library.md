---
entities:
- {entity: folder, shows: [Name, Icon, Pinned, Lock type, Bookmark count, Unread count]}
- {entity: bookmark, shows: [Title, Site, Description, Tags, Read, Reminder, Reading time, Content kind, Folder, Link]}
- {entity: tag, shows: [Name, Color]}
- {entity: tag-suggestion, shows: [Tag]}
references:
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/(tabs)/index.tsx
---

# Library

The home list: pinned and other folders, unfiled bookmarks, and search across the whole library with its filters.
