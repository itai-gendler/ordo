---
kind: primary
routes:
  app: App
steps:
- text: The Account holder unlocks the folder, chooses Lock folder and sets a new lock
  kind: actor
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product replaces the lock and ends every current unlock of the folder
  kind: product
  actor: account-holder
  entities:
  - {entity: folder, effect: changes, facts: [Lock type]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Change a folder's lock

## Trigger

An Account holder wants a new password, PIN, pattern or lock type on a locked folder.

## Outcome

The folder is locked with the new secret, and earlier unlocks no longer work.
