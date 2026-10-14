---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Export under Data, a format, and Entire library or some folders
  kind: actor
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
- text: The Product writes the bookmarks with their folders, tags and reading state
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: reads, facts: [Link, Title, Description, Author, Published on, Reading time, Folder, Tags, Read, Reading progress, Finished at, Saved at]}
  - {entity: folder, effect: reads, facts: [Name, Icon, Pinned]}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
- text: The Account holder saves the file
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
---

# Export the library

## Trigger

An Account holder wants a copy of their bookmarks.

## Outcome

The Account holder has saved an export file.

## Edge cases

- An export carries no article text.
