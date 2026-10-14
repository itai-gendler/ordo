---
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/highlights.service.ts#HighlightsService
---

# Highlight

A highlighted passage of a bookmark's article.

## Information kept

- **Passage** — the highlighted text, up to 2,000 characters
- **Text before** — a little of the text just before the passage, used to find it again
- **Text after** — a little of the text just after the passage
- **Link** — the link inside the passage, when it has one
- **Highlighted at** — when the passage was highlighted
