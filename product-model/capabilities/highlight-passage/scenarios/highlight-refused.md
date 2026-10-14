---
kind: validation
routes:
  app: App
steps:
- text: The Account holder selects text and chooses Highlight
  kind: actor
  actor: account-holder
  entities:
  - {entity: highlight, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
- text: The selection is over 2,000 characters, is not in the stored article, or the bookmark already has 100 highlights
  kind: condition
  actor: account-holder
  entities:
  - {entity: highlight, effect: reads, facts: [Passage]}
  - {entity: bookmark, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
- text: The Product explains why and keeps the highlights as they were
  kind: product
  actor: account-holder
  entities:
  - {entity: highlight, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
---

# The highlight cannot be kept

## Trigger

An Account holder highlights a passage the Product cannot keep.

## Outcome

Nothing is highlighted.
