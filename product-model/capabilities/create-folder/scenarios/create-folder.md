---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses New folder, enters a name and may pick an icon
  kind: actor
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product creates the folder after the existing ones
  kind: product
  actor: account-holder
  entities:
  - {entity: folder, effect: creates, to: Not locked, facts: [Name, Icon, Pinned, Created at]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Create a folder

## Trigger

An Account holder wants to file bookmarks together.

## Outcome

The new folder is in the library, after the existing ones.

## Edge cases

- A folder name has 1 to 100 characters; without a choice the folder gets the default folder icon.
