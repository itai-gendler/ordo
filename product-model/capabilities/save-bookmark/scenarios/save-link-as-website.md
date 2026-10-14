---
kind: primary
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
- text: The Product fetches the page, finds no article in it and keeps the link as a website
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: changes, from: Fetching, to: Website, facts: [Title, Fetch problem]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Save a link that stays a website

## Trigger

An Account holder saves a link whose page is not an article, such as a video or an app.

## Outcome

The bookmark is in the library as a website that opens in a browser.
