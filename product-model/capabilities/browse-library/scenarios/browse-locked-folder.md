---
kind: validation
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
- text: The folder is locked and not unlocked on this device
  kind: condition
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: [Lock type]}
  contexts:
    app: {place: 'ordo-app::signed-in::folder'}
- text: The Product shows "This folder is locked" with Unlock
  kind: product
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::folder'}
---

# Open a locked folder

## Trigger

An Account holder opens a folder that is locked and not unlocked on this device.

## Outcome

The folder's bookmarks stay hidden until the folder is unlocked.
