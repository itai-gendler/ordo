---
kind: validation
routes:
  app: App
steps:
- text: The Account holder deletes a folder
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
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product refuses with "This folder is locked."
  kind: product
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Delete a locked folder

## Trigger

An Account holder deletes a locked folder they have not unlocked on this device.

## Outcome

The folder and its bookmarks are kept.
