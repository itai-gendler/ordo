---
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/tag-suggestions.ts#scoreTagSuggestions
---

# Tag suggestion

One of the account's existing tags that the Product suggests for a bookmark from its title, description, site and article.

## Information kept

- **Tag** — the existing tag the Product suggests for the bookmark

## States

### Suggested

Offered in Edit tags.

### Dismissed

Turned down; the tag is not suggested for that bookmark again.
