---
kind: primary
routes:
  app: App
steps:
- text: The Account holder types in the search bar and may filter by folders, tags, read status, articles or websites, due or upcoming reminders, or fuzzy match
  kind: actor
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product matches titles, sites, links, descriptions and tag names, and article text for longer words, and ranks the results
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: reads, facts: [Title, Site, Link, Description, Tags, Article, Read, Reminder, Content kind]}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Search the library

## Trigger

An Account holder looks for a bookmark they saved.

## Outcome

The Account holder sees the matching bookmarks, best matches first.

## Edge cases

- Searching ignores accents.
