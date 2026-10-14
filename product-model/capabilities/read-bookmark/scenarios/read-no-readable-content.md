---
kind: edge
routes:
  app: App
steps:
- text: The Account holder opens the bookmark
  kind: actor
  actor: account-holder
  entities:
  - {entity: bookmark, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The page could not be fetched
  kind: condition
  actor: account-holder
  entities:
  - {entity: bookmark, effect: reads, facts: [Fetch problem]}
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
- text: The Product shows "No readable content" with Open original
  kind: product
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
---

# No readable content

## Trigger

An Account holder opens a bookmark whose page could not be fetched.

## Outcome

The Account holder can open the original page instead.
