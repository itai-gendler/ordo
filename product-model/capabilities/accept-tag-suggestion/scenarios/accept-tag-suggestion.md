---
kind: primary
routes:
  app: App
steps:
- text: The Account holder accepts a suggested tag in Edit tags and chooses Save
  kind: actor
  actor: account-holder
  entities:
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product puts the tag on the bookmark and drops the suggestion
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: changes, facts: [Tags]}
  - {entity: tag-suggestion, effect: removes, from: Suggested}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Accept a suggested tag

## Trigger

An Account holder sees a suggested tag that fits the bookmark.

## Outcome

The bookmark carries the tag and the suggestion is gone.
