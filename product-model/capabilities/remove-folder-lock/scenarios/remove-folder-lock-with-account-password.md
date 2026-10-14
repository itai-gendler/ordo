---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Remove lock and enters their sign-in password in place of the folder's secret
  kind: actor
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product checks the account password
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: reads, facts: [Password]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product removes the lock
  kind: product
  actor: account-holder
  entities:
  - {entity: folder, effect: changes, from: Locked, to: Not locked, facts: [Lock type]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Remove a lock with the account password

## Trigger

An Account holder forgot a folder's secret, or the device that holds its device lock is gone.

## Outcome

The folder is no longer locked.
