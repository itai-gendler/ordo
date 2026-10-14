---
entities:
- {entity: folder, shows: [Name, Bookmark count, Lock type]}
- {entity: bookmark, shows: [Title, Site, Description, Tags, Read, Reminder, Reading time, Content kind]}
references:
- kind: code
  role: implementation
  target: apps/mobile/app/(app)/folder/[id].tsx
---

# Folder

One folder's bookmarks, or the prompt to unlock it.
