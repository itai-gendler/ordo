---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Use device lock and confirms with fingerprint or face unlock
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::folder'}
- text: The Product opens the folder on this device for 10 minutes
  kind: product
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: [Name, Lock type]}
  contexts:
    app: {place: 'ordo-app::signed-in::folder'}
---

# Unlock with the device lock

## Trigger

An Account holder opens a folder locked with the device lock.

## Outcome

The folder is open on this device for 10 minutes.
