---
kind: validation
routes:
  app: App
steps:
- text: The Account holder opens the bookmark
  kind: actor
  actor: account-holder
  entities:
  - {entity: bookmark, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The bookmark's folder is locked and not unlocked on this device
  kind: condition
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: [Lock type]}
  - {entity: bookmark, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
- text: The Product shows "This folder is locked" with Unlock
  kind: product
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
---

# Read a bookmark in a locked folder

## Trigger

An Account holder opens a bookmark from a reminder or link while its folder is locked.

## Outcome

The bookmark stays hidden until its folder is unlocked.
