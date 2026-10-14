---
relations:
- entity: tag-suggestion
  verb: suggested as
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/tags.service.ts#TagsService
---

# Tag

A colored label the account holder puts on bookmarks.

## Information kept

- **Name** — up to 40 characters, unique within the account whatever the capitalization
- **Color** — one of ten colors; blue by default
- **Bookmark count** — how many visible bookmarks carry the tag
