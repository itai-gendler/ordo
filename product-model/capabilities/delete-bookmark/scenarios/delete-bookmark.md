---
kind: primary
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
- text: The Product takes the bookmark off the list and offers Undo for a few seconds
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product deletes the bookmark with its highlights and suggestions once Undo is no longer offered
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: removes, from: Article}
  - {entity: highlight, effect: removes, with: bookmark}
  - {entity: tag-suggestion, effect: removes, from: Suggested, with: bookmark}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Delete a bookmark

## Trigger

An Account holder no longer wants a bookmark.

## Outcome

The bookmark, its highlights and its tag suggestions are gone.

## Edge cases

- Several selected bookmarks can be deleted at once.
