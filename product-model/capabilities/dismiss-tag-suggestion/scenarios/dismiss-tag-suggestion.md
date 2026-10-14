---
kind: primary
routes:
  app: App
steps:
- text: The Account holder dismisses a suggested tag in Edit tags and chooses Save
  kind: actor
  actor: account-holder
  entities:
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product dismisses the suggestion
  kind: product
  actor: account-holder
  entities:
  - {entity: tag-suggestion, effect: changes, from: Suggested, to: Dismissed, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Dismiss a suggested tag

## Trigger

An Account holder sees a suggested tag that does not fit.

## Outcome

The suggestion is dismissed for good on this bookmark.
