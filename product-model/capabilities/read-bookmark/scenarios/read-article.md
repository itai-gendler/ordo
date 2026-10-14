---
kind: primary
routes:
  app: App
steps:
- text: The Account holder opens the bookmark
  kind: actor
  actor: account-holder
  entities:
  - {entity: bookmark, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product shows the article in the reader with its highlights
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: reads, facts: [Title, Site, Author, Published on, Reading time, Article]}
  - {entity: highlight, effect: reads, facts: [Passage]}
  - {entity: account, effect: reads, facts: [Reader text size, Reader typeface, Reader line spacing, Reader theme, Reader AMOLED black]}
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
- text: The Account holder reads and scrolls
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
- text: The Product saves the reading progress and marks the bookmark read at the end of the article
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: changes, facts: [Reading progress, Read, Finished at]}
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
---

# Read an article

## Trigger

An Account holder opens a bookmark kept as an article.

## Outcome

The Account holder has read the article; reaching its end marks the bookmark read.

## Edge cases

- Opening a bookmark whose reminder is due clears the reminder; an upcoming reminder stays.
- The Highlights panel lists the article's highlights and jumps to one.
- Open original opens the saved page in a browser from the article.
