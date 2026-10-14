---
kind: primary
routes:
  app: App
steps:
- text: The Account holder opens a locked folder and enters its password, PIN or pattern
  kind: actor
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::folder'}
- text: The Product checks the secret and opens the folder on this device for 10 minutes
  kind: product
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: [Name, Lock type]}
  contexts:
    app: {place: 'ordo-app::signed-in::folder'}
---

# Unlock a folder

## Trigger

An Account holder wants to see a locked folder's bookmarks.

## Outcome

The folder's bookmarks show in the folder, the library, search and tags on this device for 10 minutes.
