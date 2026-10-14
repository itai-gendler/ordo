---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Delete folder and confirms that the folder and every bookmark inside it will be deleted
  kind: actor
  actor: account-holder
  entities:
  - {entity: bookmark, effect: reads, facts: []}
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product takes the folder off the list and offers Undo for a few seconds
  kind: product
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product deletes the folder and its bookmarks once Undo is no longer offered
  kind: product
  actor: account-holder
  entities:
  - {entity: folder, effect: removes, from: Not locked}
  - {entity: bookmark, effect: removes, from: Article, with: folder}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Delete a folder and its bookmarks

## Trigger

An Account holder no longer wants a folder or what is in it.

## Outcome

The folder and its bookmarks are gone.

## Edge cases

- Several selected folders can be deleted at once.
