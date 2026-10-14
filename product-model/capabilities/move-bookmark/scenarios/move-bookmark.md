---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Move to folder and picks a folder or the unfiled list
  kind: actor
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product files the bookmark there
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: changes, facts: [Folder]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Move a bookmark

## Trigger

An Account holder wants a bookmark in another folder.

## Outcome

The bookmark is in the chosen folder, or unfiled.

## Edge cases

- Several selected bookmarks can be moved at once, also by dragging them onto a folder.
- Moving into or out of a locked folder needs it unlocked on this device.
