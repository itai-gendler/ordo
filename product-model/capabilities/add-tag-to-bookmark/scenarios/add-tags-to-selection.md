---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Add tags for the selection and picks tags
  kind: actor
  actor: account-holder
  entities:
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product adds the tags to each bookmark that has room, without passing 20 tags on any
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: changes, facts: [Tags]}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Add tags to several bookmarks

## Trigger

An Account holder selected several bookmarks.

## Outcome

Each selected bookmark carries the tags, up to its limit.
