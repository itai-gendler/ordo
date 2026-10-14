---
kind: validation
routes:
  app: App
steps:
- text: The Account holder picks a file to import
  kind: actor
  actor: account-holder
  entities:
  - {entity: import, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
- text: The Product starts reading the file
  kind: product
  actor: account-holder
  entities:
  - {entity: import, effect: creates, to: Reading file, facts: [File name]}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
- text: The Product cannot read it and says "Couldn't import" with the reason
  kind: product
  actor: account-holder
  entities:
  - {entity: import, effect: changes, from: Reading file, to: Failed, facts: [Problem]}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
---

# The file cannot be read

## Trigger

An Account holder picks a file that is not a bookmarks file ordo understands.

## Outcome

Nothing is imported.
