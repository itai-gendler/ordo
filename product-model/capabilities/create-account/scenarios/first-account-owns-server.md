---
kind: primary
routes:
  app: App
steps:
- text: The Visitor enters a display name, an email and a password twice
  kind: actor
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::create-account'}
- text: The server has no account yet, so it takes this one whatever its sign-ups setting
  kind: condition
  actor: visitor
  entities:
  - {entity: server, effect: reads, facts: [Has accounts, Sign-ups]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-out::create-account'}
- text: The Product creates the active account
  kind: product
  actor: visitor
  entities:
  - {entity: account, effect: creates, to: Active, facts: [Display name, Email, Password, Member since]}
  contexts:
    app: {place: 'ordo-app::signed-out::create-account'}
- text: The Product records the new account as the server's owner
  kind: product
  actor: visitor
  entities:
  - {entity: server, effect: changes, facts: [Owner, Has accounts]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-out::create-account'}
- text: The Product signs the new account in on this device
  kind: product
  actor: visitor
  entities:
  - {entity: session, effect: creates, facts: [Device name, Device type, Signed in at, Last active, This device]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-out::create-account'}
---

# The first account owns the server

## Trigger

A Visitor creates the first account on a newly installed server.

## Outcome

The first account exists and owns the server, even though sign-ups are closed.
