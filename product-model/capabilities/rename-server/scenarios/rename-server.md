---
kind: primary
routes:
  app: App
steps:
- text: The Server owner chooses Edit server under Hosting, enters a name and saves
  kind: actor
  actor: server-owner
  entities:
  - {entity: server, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::hosting'}
- text: The Product saves the server's name
  kind: product
  actor: server-owner
  entities:
  - {entity: server, effect: changes, facts: [Name]}
  contexts:
    app: {place: 'ordo-app::signed-in::hosting'}
---

# Rename the server

## Trigger

The Server owner wants the app to show a name of their choosing.

## Outcome

Everyone using the server sees the new name.
