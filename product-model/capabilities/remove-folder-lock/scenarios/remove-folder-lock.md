---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Remove lock and enters the folder's secret, or confirms with the device lock
  kind: actor
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product removes the lock and ends every current unlock of the folder
  kind: product
  actor: account-holder
  entities:
  - {entity: folder, effect: changes, from: Locked, to: Not locked, facts: [Lock type]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Remove a folder's lock

## Trigger

An Account holder no longer wants a folder locked.

## Outcome

The folder is no longer locked.
