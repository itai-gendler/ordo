---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Remove highlight on a highlight in the article or the Highlights panel
  kind: actor
  actor: account-holder
  entities:
  - {entity: highlight, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
- text: The Product removes it and says "Highlight removed"
  kind: product
  actor: account-holder
  entities:
  - {entity: highlight, effect: removes}
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
---

# Remove a highlight

## Trigger

An Account holder no longer wants a highlight.

## Outcome

The highlight is gone.
