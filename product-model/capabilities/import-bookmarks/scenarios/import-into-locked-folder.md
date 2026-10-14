---
kind: validation
routes:
  app: App
steps:
- text: The Account holder confirms Import with All at once on
  kind: actor
  actor: account-holder
  entities:
  - {entity: import, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
- text: The file matches locked folders that are not unlocked on this device
  kind: condition
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: [Name, Lock type]}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
- text: The Product imports nothing and asks to unlock those folders first
  kind: product
  actor: account-holder
  entities:
  - {entity: import, effect: changes, from: Ready, to: Failed, facts: [Duplicate handling, All at once, Problem]}
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
---

# Locked folders stop an all-at-once import

## Trigger

The file imports into folders the Account holder locked and has not unlocked on this device.

## Outcome

Nothing is imported and the Account holder is told which folders to unlock.
