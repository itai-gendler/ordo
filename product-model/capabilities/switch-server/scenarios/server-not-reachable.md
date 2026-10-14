---
kind: validation
routes:
  app: App
steps:
- text: The Visitor enters a server address
  kind: actor
  actor: visitor
  entities:
  - {entity: server, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in'}
- text: The address does not answer as an ordo server
  kind: condition
  actor: visitor
  entities:
  - {entity: server, effect: reads, facts: [Version]}
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in'}
- text: The Product explains what was wrong and keeps the current server
  kind: product
  actor: visitor
  entities:
  - {entity: server, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in'}
---

# The address is not an ordo server

## Trigger

A Visitor enters an address that does not answer as an ordo server.

## Outcome

The app keeps its current server.
