---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Edit tags, picks tags and chooses Save
  kind: actor
  actor: account-holder
  entities:
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product puts the tags on the bookmark
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: changes, facts: [Tags]}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Add a tag in Edit tags

## Trigger

An Account holder wants to group a bookmark with others.

## Outcome

The bookmark carries the tag.
