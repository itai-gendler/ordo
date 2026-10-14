---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Mark as article
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
- text: The Product records the choice and fetches the page again as an article
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: changes, from: Website, to: Fetching, facts: [Content kind]}
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
- text: The Product keeps the article and says "Saved as an article"
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: changes, from: Fetching, to: Article, facts: [Title, Description, Author, Published on, Reading time, Article]}
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
---

# Read a website as an article

## Trigger

An Account holder knows a page kept as a website has an article in it.

## Outcome

The bookmark opens in the reader as an article.

## Edge cases

- When the page still has no text to read, the reader offers to open the original page.
