---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Change icon on a folder, picks one and chooses Save icon
  kind: actor
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product saves the icon
  kind: product
  actor: account-holder
  entities:
  - {entity: folder, effect: changes, facts: [Icon]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Change a folder's icon

## Trigger

An Account holder wants a folder to stand out.

## Outcome

The folder shows the new icon.
