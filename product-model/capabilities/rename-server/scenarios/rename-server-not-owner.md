---
kind: validation
routes:
  app: App
steps:
- text: The Account holder chooses Edit server under Hosting
  kind: actor
  actor: account-holder
  entities:
  - {entity: server, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::hosting'}
- text: The Account holder does not own the server, or the server does not allow renaming
  kind: condition
  actor: account-holder
  entities:
  - {entity: server, effect: reads, facts: [Name, Renaming allowed]}
  contexts:
    app: {place: 'ordo-app::signed-in::hosting'}
- text: The Product offers the address but not the name
  kind: product
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::hosting'}
---

# Only the owner names the server

## Trigger

An Account holder who does not own the server opens Edit server.

## Outcome

The name is unchanged.
