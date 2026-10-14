---
kind: validation
routes:
  app: App
steps:
- text: The Visitor enters an email and password
  kind: actor
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in'}
- text: No account has that email, or the password does not match
  kind: condition
  actor: visitor
  entities:
  - {entity: account, effect: reads, facts: [Email, Password]}
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in'}
- text: The Product refuses with "Incorrect email or password."
  kind: product
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in'}
---

# Incorrect email or password

## Trigger

A Visitor enters an email or password that does not match an account.

## Outcome

The device stays signed out.
