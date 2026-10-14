---
kind: primary
routes:
  app: App
steps:
- text: The Account holder opens a tag
  kind: actor
  actor: account-holder
  entities:
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::tags'}
- text: The Product lists the visible bookmarks carrying the tag
  kind: product
  actor: account-holder
  entities:
  - {entity: tag, effect: reads, facts: [Name, Color]}
  - {entity: bookmark, effect: reads, facts: [Title, Site, Description, Tags, Read, Reminder, Reading time, Content kind]}
  contexts:
    app: {place: 'ordo-app::signed-in::tag'}
---

# Open a tag

## Trigger

An Account holder wants every bookmark carrying one tag.

## Outcome

The Account holder sees the bookmarks with that tag.
