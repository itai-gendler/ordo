---
kind: primary
routes:
  app: App
steps:
- text: The Account holder selects highlighted text and chooses Remove highlight
  kind: actor
  actor: account-holder
  entities:
  - {entity: highlight, as: kept, effect: reads, facts: [Passage]}
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
- text: The Product trims the highlight, splitting it in two when the selection was in its middle
  kind: product
  actor: account-holder
  entities:
  - {entity: highlight, as: kept, effect: changes, facts: [Passage, Text before, Text after]}
  - {entity: highlight, as: split, effect: creates, facts: [Passage, Text before, Text after, Link, Highlighted at]}
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
- text: The Product confirms the change
  kind: product
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
---

# Remove part of a highlight

## Trigger

An Account holder wants only some of a highlighted passage highlighted.

## Outcome

Only the unselected parts stay highlighted.
