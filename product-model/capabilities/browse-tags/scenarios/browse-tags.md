---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Manage tags
  kind: actor
  actor: account-holder
  entities:
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::tags'}
- text: The Product lists the tags with their colors and visible bookmark counts, most used first
  kind: product
  actor: account-holder
  entities:
  - {entity: tag, effect: reads, facts: [Name, Color, Bookmark count]}
  - {entity: bookmark, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::tags'}
---

# Browse tags

## Trigger

An Account holder chooses Manage tags.

## Outcome

The Account holder sees their tags, most used first.

## Edge cases

- Bookmarks in locked folders count only while the folder is unlocked on this device.
