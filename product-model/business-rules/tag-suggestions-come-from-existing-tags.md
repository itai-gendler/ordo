---
appliesTo:
- type: capability
  id: save-bookmark
- type: capability
  id: dismiss-tag-suggestion
- type: capability
  id: accept-tag-suggestion
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/tag-suggestions.ts#scoreTagSuggestions
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/tag-suggestion.service.ts#TagSuggestionService
---

# Suggested tags are only the account's own tags, never one already dismissed

After a page is fetched, the Product suggests at most three of the account's existing tags that match the bookmark's title, description, site or article. It never invents a tag, never suggests a tag the bookmark carries, and never suggests again a tag dismissed for that bookmark.
