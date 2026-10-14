---
kind: primary
routes:
  app: App
steps:
- text: The Visitor chooses Use your own server on the sign-in screen
  kind: actor
  actor: visitor
  entities:
  - {entity: server, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in'}
- text: The Visitor agrees that Axolet is not responsible for their server or data, and enters the server address
  kind: actor
  actor: visitor
  entities:
  - {entity: server, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in'}
- text: The Product checks that the address answers as an ordo server
  kind: product
  actor: visitor
  entities:
  - {entity: server, effect: reads, facts: [Name, Version]}
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in'}
- text: The Product keeps the new address on this device
  kind: product
  actor: visitor
  entities:
  - {entity: device-settings, effect: changes, facts: [Server address]}
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in'}
---

# Use your own server before signing in

## Trigger

A Visitor wants to use a server they run instead of ordo Cloud.

## Outcome

The app talks to the Visitor's server and the sign-in screen names it.
