---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Lock folder, picks Device lock and confirms with the device's fingerprint or face unlock
  kind: actor
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product locks the folder with a key kept on this device
  kind: product
  actor: account-holder
  entities:
  - {entity: folder, effect: changes, from: Not locked, to: Locked, facts: [Lock type]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Lock a folder with the device lock

## Trigger

An Account holder wants to open a folder with their fingerprint or face.

## Outcome

The folder is locked and opens with the device's unlock on this device.

## Edge cases

- Device lock needs fingerprint or face unlock set up on the device first.
- On another device the folder opens by removing the lock with the account password.
