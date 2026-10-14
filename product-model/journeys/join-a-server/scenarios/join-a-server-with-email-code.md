---
kind: primary
result: achieved
routes:
  app: App
steps:
- text: The Visitor creates an account with a display name, email and password
  kind: actor
  actor: visitor
  entities:
  - {entity: account, effect: creates, to: Awaiting email verification, facts: [Display name, Email, Password, Member since]}
  contexts:
    app: {place: 'ordo-app::signed-out::create-account'}
  capability: create-account
- text: The Product emails a code and opens the code screen
  kind: product
  actor: visitor
  entities:
  - {entity: account, effect: reads, facts: [Email]}
  contexts:
    app: {place: 'ordo-app::signed-out::verify-email'}
  capability: create-account
- text: The Visitor enters the emailed code
  kind: actor
  actor: visitor
  entities:
  - {entity: account, effect: changes, from: Awaiting email verification, to: Active, facts: [Email verified]}
  contexts:
    app: {place: 'ordo-app::signed-out::verify-email'}
  capability: verify-email
- text: The Product opens sign-in
  kind: product
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in'}
  capability: verify-email
- text: The Visitor signs in with their email and password
  kind: actor
  actor: visitor
  entities:
  - {entity: session, effect: creates, facts: [Device name, Device type, Signed in at, Last active, This device]}
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in'}
  capability: sign-in
---

# Create an account, confirm it and sign in

## Trigger

A Visitor creates an account on a server that requires email verification.

## Outcome

The account is active and the device is signed in.
