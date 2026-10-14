---
kind: validation
routes:
  app: App
steps:
- text: The Account holder enters a tag name
  kind: actor
  actor: account-holder
  entities:
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::tags'}
- text: Another of the account's tags has the same name, ignoring capitalization and extra spaces
  kind: condition
  actor: account-holder
  entities:
  - {entity: tag, effect: reads, facts: [Name]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::tags'}
- text: The Product refuses with "A tag with this name already exists."
  kind: product
  actor: account-holder
  entities:
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::tags'}
---

# The tag name is taken

## Trigger

An Account holder enters a name an existing tag already has, in any capitalization.

## Outcome

No tag is created.
