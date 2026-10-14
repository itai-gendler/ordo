---
kind: primary
routes:
  app: App
steps:
- text: The Account holder opens a folder
  kind: actor
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product lists the folder's bookmarks
  kind: product
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: [Name, Bookmark count]}
  - {entity: bookmark, effect: reads, facts: [Title, Site, Description, Tags, Read, Reminder, Reading time, Content kind]}
  contexts:
    app: {place: 'ordo-app::signed-in::folder'}
---

# Open a folder

## Trigger

An Account holder wants the bookmarks in one folder.

## Outcome

The Account holder sees the folder's bookmarks.
