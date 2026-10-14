---
kind: edge
routes:
  app: App
steps:
- text: The Account holder chooses Delete bookmark and confirms
  kind: actor
  actor: account-holder
  entities:
  - {entity: bookmark, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product takes the bookmark off the list and offers Undo
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Account holder chooses Undo
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product puts the bookmark back and deletes nothing
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: reads, facts: [Title]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Undo a deletion

## Trigger

An Account holder deleted a bookmark by mistake.

## Outcome

The bookmark is back where it was.
