---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses New tag, enters a name and may pick a color
  kind: actor
  actor: account-holder
  entities:
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::tags'}
- text: The Product creates the tag, blue unless another color was picked
  kind: product
  actor: account-holder
  entities:
  - {entity: tag, effect: creates, facts: [Name, Color]}
  contexts:
    app: {place: 'ordo-app::signed-in::tags'}
---

# Create a tag

## Trigger

An Account holder wants a new label for bookmarks.

## Outcome

The new tag is available for bookmarks and suggestions.
