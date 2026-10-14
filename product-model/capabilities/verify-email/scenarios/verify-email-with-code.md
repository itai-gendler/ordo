---
kind: primary
routes:
  app: App
steps:
- text: The Visitor enters the email and the 6-digit code
  kind: actor
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::verify-email'}
- text: The Product checks the code against the latest one sent for that account
  kind: product
  actor: visitor
  entities:
  - {entity: account, effect: reads, facts: [Email]}
  contexts:
    app: {place: 'ordo-app::signed-out::verify-email'}
- text: The Product marks the account's email verified
  kind: product
  actor: visitor
  entities:
  - {entity: account, effect: changes, from: Awaiting email verification, to: Active, facts: [Email verified]}
  contexts:
    app: {place: 'ordo-app::signed-out::verify-email'}
- text: The Product says "Email verified. You can sign in now." and opens sign-in
  kind: product
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in'}
---

# Confirm the email with the code

## Trigger

A Visitor has the code the Product emailed after they created an account.

## Outcome

The account is active and the Visitor is on the sign-in screen.
