---
kind: edge
routes:
  app: App
steps:
- text: The Account holder closes the import without confirming
  kind: actor
  actor: account-holder
  entities:
  - {entity: import, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
- text: The Product discards the staged import
  kind: product
  actor: account-holder
  entities:
  - {entity: import, effect: removes, from: Ready}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
---

# Close the import before confirming

## Trigger

An Account holder looks at the preview and decides not to import.

## Outcome

Nothing is imported and the staged file is discarded.

## Edge cases

- A staged import left alone is discarded after an hour.
