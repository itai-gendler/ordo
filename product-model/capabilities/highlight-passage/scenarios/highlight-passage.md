---
kind: primary
routes:
  app: App
steps:
- text: The Account holder selects text in the article and chooses Highlight
  kind: actor
  actor: account-holder
  entities:
  - {entity: highlight, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
- text: The Product keeps the passage with a little of the text around it so it can be found again
  kind: product
  actor: account-holder
  entities:
  - {entity: highlight, effect: creates, facts: [Passage, Text before, Text after, Link, Highlighted at]}
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
- text: The Product marks the passage in the article and says "Highlighted"
  kind: product
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
---

# Highlight a passage

## Trigger

An Account holder reads a passage worth keeping.

## Outcome

The passage is highlighted in the article and listed under Highlights.
