---
appliesTo:
- type: capability
  id: highlight-passage
- type: capability
  id: remove-highlight
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/highlights.service.ts#HighlightsService
- kind: code
  role: implementation
  target: packages/shared/src/constants.ts#HIGHLIGHTS_PER_BOOKMARK_MAX
---

# A bookmark's highlights never overlap, and there are at most 100

A new highlight that overlaps or touches others joins them into one, and removing part of a highlight trims or splits it. A bookmark holds at most 100 highlights of up to 2,000 characters each.
