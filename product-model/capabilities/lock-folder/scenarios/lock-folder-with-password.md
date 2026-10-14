---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Lock folder, picks Text password and enters a password of at least 4 characters twice
  kind: actor
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product locks the folder
  kind: product
  actor: account-holder
  entities:
  - {entity: folder, effect: changes, from: Not locked, to: Locked, facts: [Lock type]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Lock a folder with a password

## Trigger

An Account holder wants a folder kept out of sight.

## Outcome

The folder is locked and its bookmarks are hidden until it is unlocked.
