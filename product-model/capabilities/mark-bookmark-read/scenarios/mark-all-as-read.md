---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Mark all as read in a folder
  kind: actor
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::folder'}
- text: The Product marks every unread bookmark in that folder read
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: changes, facts: [Read, Finished at]}
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::folder'}
---

# Mark all as read

## Trigger

An Account holder wants to clear everything unread in a folder or in the unfiled list.

## Outcome

Every bookmark there is read.

## Edge cases

- From the library home, Mark all as read covers only unfiled bookmarks.
