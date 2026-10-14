---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Edit tag, changes the name or color and chooses Save
  kind: actor
  actor: account-holder
  entities:
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::tags'}
- text: The Product saves the tag
  kind: product
  actor: account-holder
  entities:
  - {entity: tag, effect: changes, facts: [Name, Color]}
  contexts:
    app: {place: 'ordo-app::signed-in::tags'}
---

# Edit a tag

## Trigger

An Account holder wants a tag named or colored differently.

## Outcome

Every bookmark carrying the tag shows the change.

## Edge cases

- A name another tag already has is refused.
