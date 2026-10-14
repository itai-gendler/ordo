---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Mark as read on a bookmark
  kind: actor
  actor: account-holder
  entities:
  - {entity: bookmark, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product marks it read and records when
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: changes, facts: [Read, Finished at]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Mark a bookmark read

## Trigger

An Account holder finished a bookmark or does not need to read it.

## Outcome

The bookmark is read.

## Edge cases

- Several selected bookmarks can be marked read at once.
