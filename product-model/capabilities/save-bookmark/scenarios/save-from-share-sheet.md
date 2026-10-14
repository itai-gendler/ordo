---
kind: primary
routes:
  app: App
steps:
- text: The Account holder shares a link to ordo from another app
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product opens Save bookmark with the link filled in
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Account holder may pick a folder and tags and chooses Save bookmark
  kind: actor
  actor: account-holder
  entities:
  - {entity: bookmark, effect: reads, facts: []}
  - {entity: folder, effect: reads, facts: []}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product saves the bookmark and fetches it in the background
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: creates, to: Fetching, facts: [Link, Title, Site, Folder, Tags, Read, Content kind, Saved at]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Save a link shared from another app

## Trigger

An Account holder shares a link to ordo from another app.

## Outcome

The bookmark is saved where the Account holder chose.
