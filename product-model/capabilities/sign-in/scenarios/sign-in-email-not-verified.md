---
kind: validation
routes:
  app: App
steps:
- text: The Visitor enters their email and password
  kind: actor
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in'}
- text: The server requires email verification and the account's email is not verified
  kind: condition
  actor: visitor
  entities:
  - {entity: server, effect: reads, facts: [Email verification required]}
  - {entity: account, effect: reads, facts: [Email verified]}
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in'}
- text: The Product refuses with "Please verify your email before signing in."
  kind: product
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in'}
---

# The email is not verified yet

## Trigger

A Visitor signs in to an account still waiting for email verification on a server that requires it.

## Outcome

The device stays signed out until the email is verified.
