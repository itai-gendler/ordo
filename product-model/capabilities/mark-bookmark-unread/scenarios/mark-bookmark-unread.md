---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Mark as unread on a bookmark
  kind: actor
  actor: account-holder
  entities:
  - {entity: bookmark, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product marks it unread and clears when it was finished
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: changes, facts: [Read, Finished at]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Mark a bookmark unread

## Trigger

An Account holder wants to come back to a bookmark.

## Outcome

The bookmark is unread.
