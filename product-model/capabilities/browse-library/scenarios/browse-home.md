---
kind: primary
routes:
  app: App
steps:
- text: The Account holder opens the library
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product lists folders, pinned first, then unfiled bookmarks, in the order the Account holder sorted them
  kind: product
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: [Name, Icon, Pinned, Lock type, Bookmark count, Unread count]}
  - {entity: bookmark, effect: reads, facts: [Title, Site, Description, Tags, Read, Reminder, Reading time, Content kind]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Browse the library

## Trigger

An Account holder opens the app.

## Outcome

The Account holder sees their folders, pinned first, and their unfiled bookmarks.

## Edge cases

- Folders and bookmarks sort by newest, oldest or title, chosen under Sort library.
