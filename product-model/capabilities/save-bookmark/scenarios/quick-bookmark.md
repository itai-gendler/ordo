---
kind: primary
routes:
  app: App
steps:
- text: The Account holder shares a link to the Quick Bookmark target
  kind: actor
  actor: account-holder
  entities:
  - {entity: bookmark, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product saves the link unfiled without opening the app and confirms it was saved
  kind: product
  actor: account-holder
  entities:
  - {entity: device-settings, effect: reads, facts: [Quick Bookmark, Show alongside Save]}
  - {entity: bookmark, effect: creates, to: Fetching, facts: [Link, Title, Site, Folder, Read, Content kind, Saved at]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Save a shared link with Quick Bookmark

## Trigger

An Account holder who turned on Quick Bookmark shares a link to ordo.

## Outcome

The bookmark is saved unfiled without opening the app.
