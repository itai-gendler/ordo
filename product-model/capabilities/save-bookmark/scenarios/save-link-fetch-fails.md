---
kind: edge
routes:
  app: App
steps:
- text: The Account holder saves a link
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product saves the bookmark at once
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: creates, to: Fetching, facts: [Link, Title, Site, Folder, Tags, Read, Content kind, Saved at]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product cannot fetch the page and records why
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: changes, from: Fetching, to: Fetch failed, facts: [Fetch problem]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# The page cannot be fetched

## Trigger

An Account holder saves a link whose site cannot be reached.

## Outcome

The bookmark is saved, and the reader offers to open the original page.
