---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Unpin folder
  kind: actor
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product unpins the folder
  kind: product
  actor: account-holder
  entities:
  - {entity: folder, effect: changes, facts: [Pinned]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Unpin a folder

## Trigger

An Account holder no longer needs a folder at the top.

## Outcome

The folder takes its place among the other folders.
