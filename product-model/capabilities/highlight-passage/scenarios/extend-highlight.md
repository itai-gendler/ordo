---
kind: primary
routes:
  app: App
steps:
- text: The Account holder selects text overlapping a highlight and chooses Highlight
  kind: actor
  actor: account-holder
  entities:
  - {entity: highlight, as: kept, effect: reads, facts: [Passage]}
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
- text: The Product joins the selection and the highlights it touches into one highlight
  kind: product
  actor: account-holder
  entities:
  - {entity: highlight, as: kept, effect: changes, facts: [Passage, Text before, Text after, Link]}
  - {entity: highlight, as: joined, effect: removes}
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
- text: The Product confirms the change
  kind: product
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
---

# Extend an existing highlight

## Trigger

An Account holder highlights text that overlaps or touches existing highlights.

## Outcome

One highlight covers the whole span.
