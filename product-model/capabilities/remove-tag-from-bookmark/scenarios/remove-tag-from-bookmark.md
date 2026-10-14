---
kind: primary
routes:
  app: App
steps:
- text: The Account holder removes a tag in Edit tags and chooses Save
  kind: actor
  actor: account-holder
  entities:
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product takes the tag off the bookmark
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: changes, facts: [Tags]}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Remove a tag in Edit tags

## Trigger

An Account holder no longer wants a tag on a bookmark.

## Outcome

The bookmark no longer carries the tag; the tag itself stays.
