---
kind: validation
routes:
  app: App
steps:
- text: The Visitor enters a display name, an email and a password twice
  kind: actor
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::create-account'}
- text: The server has accounts and its sign-ups are closed
  kind: condition
  actor: visitor
  entities:
  - {entity: server, effect: reads, facts: [Has accounts, Sign-ups]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-out::create-account'}
- text: The Product refuses with "This server isn't accepting new sign-ups."
  kind: product
  actor: visitor
  entities:
  - {entity: server, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-out::create-account'}
---

# Sign-ups are closed

## Trigger

A Visitor tries to create an account on a server that already has accounts and keeps sign-ups closed.

## Outcome

No account is created and the Visitor is told the server is not accepting sign-ups.
