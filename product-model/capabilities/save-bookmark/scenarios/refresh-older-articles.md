---
kind: edge
routes:
  app: App
steps:
- text: The server starts and finds bookmarks kept by an older version of its page reader
  kind: condition
  unattended: true
  entities:
  - {entity: bookmark, effect: reads, facts: [Link, Content kind]}
  - {entity: server, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product fetches those pages again in small batches and keeps the new article
  kind: product
  entities:
  - {entity: bookmark, effect: changes, facts: [Title, Description, Author, Published on, Reading time, Article]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Older articles are fetched again

## Trigger

The server is updated with a better way of reading pages.

## Outcome

Bookmarks kept by an older version are fetched again once, in the background.

## Edge cases

- Pages that were still being fetched when the server stopped are fetched again when it starts.
