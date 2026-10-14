---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Rename on a folder and enters a name
  kind: actor
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product saves the name
  kind: product
  actor: account-holder
  entities:
  - {entity: folder, effect: changes, facts: [Name]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Rename a folder

## Trigger

An Account holder wants a better name for a folder.

## Outcome

The folder has the new name.

## Edge cases

- A locked folder must be unlocked on this device first.
