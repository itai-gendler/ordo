---
relations:
- entity: bookmark
  verb: holds
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/folders.service.ts#FoldersService
- kind: code
  role: implementation
  target: apps/server/prisma/schema.prisma
---

# Folder

A named group of bookmarks in one account's library. A bookmark is in one folder or none.

## Information kept

- **Name** — the folder's name, up to 100 characters
- **Icon** — one icon from a fixed set
- **Pinned** — whether the folder is pinned to the top of the library
- **Lock type** — password, PIN, pattern or device lock, while the folder is locked
- **Bookmark count** — how many bookmarks the folder holds
- **Unread count** — how many of them are unread
- **Created at** — when the folder was created

## States

### Not locked

The folder's bookmarks show wherever the library shows.

### Locked

The folder's bookmarks stay hidden until it is unlocked on the device.
