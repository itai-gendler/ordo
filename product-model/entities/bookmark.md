---
relations:
- entity: tag
  verb: tagged with
  cardinality: many-to-many
- entity: highlight
  verb: has
  cardinality: one-to-many
- entity: tag-suggestion
  verb: has
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/bookmarks.service.ts#BookmarksService
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/extraction.service.ts#ExtractionService
- kind: code
  role: implementation
  target: apps/server/prisma/schema.prisma
---

# Bookmark

A saved link in one account's library, with the article the server kept for it, its reading state and its reminder.

## Information kept

- **Link** — the saved web address
- **Title** — the page title, or a provisional title from the link until the page is fetched
- **Description** — the page's summary
- **Site** — the site the link points to
- **Author** — the article's author, when known
- **Published on** — the article's publication date, when known
- **Reading time** — estimated minutes to read the article
- **Article** — the readable article text kept for the reader
- **Content kind** — Automatic, or Article or Website when the person chose it
- **Fetch problem** — why the page could not be kept as an article
- **Folder** — the folder holding the bookmark, or none when it is unfiled
- **Tags** — up to 20 of the person's tags
- **Read** — whether the bookmark is read
- **Reading progress** — how far through the article the person has read
- **Finished at** — when the bookmark was marked read
- **Reminder** — a date and time to be reminded about the bookmark
- **Saved at** — when the bookmark was saved

## States

### Fetching

Saved, while the server fetches the page.

### Article

The page had an article, which opens in the reader.

### Website

The page is not an article, or the person chose to open it as a website; it opens in a browser.

### Fetch failed

The page could not be fetched; the reader offers the original page.
