---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Pin folder
  kind: actor
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product pins the folder
  kind: product
  actor: account-holder
  entities:
  - {entity: folder, effect: changes, facts: [Pinned]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Pin a folder

## Trigger

An Account holder uses a folder often.

## Outcome

The folder is listed among the pinned folders at the top.
