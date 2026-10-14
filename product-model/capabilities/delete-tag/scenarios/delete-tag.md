---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Delete tag and confirms
  kind: actor
  actor: account-holder
  entities:
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::tags'}
- text: The Product takes the tag off the list and offers Undo for a few seconds
  kind: product
  actor: account-holder
  entities:
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::tags'}
- text: The Product deletes the tag and takes it off every bookmark, keeping the bookmarks
  kind: product
  actor: account-holder
  entities:
  - {entity: tag, effect: removes}
  - {entity: tag-suggestion, effect: removes, from: Suggested, with: tag}
  - {entity: bookmark, effect: changes, facts: [Tags]}
  contexts:
    app: {place: 'ordo-app::signed-in::tags'}
---

# Delete a tag

## Trigger

An Account holder no longer uses a tag.

## Outcome

The tag is gone and no bookmark carries it.
