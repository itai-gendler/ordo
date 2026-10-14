---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Mark as website
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
- text: The Product records the choice and says "Saved as a website"
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: changes, from: Article, to: Website, facts: [Content kind]}
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
---

# Open an article as a website

## Trigger

An Account holder prefers the original page to the reader for a bookmark.

## Outcome

The bookmark opens as a website.

## Edge cases

- A bookmark the Account holder earlier marked as an article returns to exactly how it was before, with its reading progress reset.
