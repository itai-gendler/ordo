---
kind: validation
routes:
  app: App
steps:
- text: The Account holder chooses folders to export
  kind: actor
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
- text: A chosen folder is locked and not unlocked on this device
  kind: condition
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: [Lock type]}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
- text: The Product refuses with "This folder is locked."
  kind: product
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
---

# Export a locked folder

## Trigger

An Account holder chooses a locked folder that is not unlocked on this device.

## Outcome

Nothing is exported until the folder is unlocked.

## Edge cases

- An Entire library export leaves out locked folders that are not unlocked on this device.
