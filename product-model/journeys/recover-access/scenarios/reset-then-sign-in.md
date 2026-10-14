---
kind: primary
result: achieved
routes:
  app: App
steps:
- text: The Visitor asks for a reset code and enters it with a new password
  kind: actor
  actor: visitor
  entities:
  - {entity: account, effect: changes, facts: [Password, Email verified]}
  contexts:
    app: {place: 'ordo-app::signed-out::reset-password'}
  capability: reset-password
- text: The Product opens sign-in with the email filled in
  kind: product
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in'}
  capability: reset-password
- text: The Visitor signs in with the new password
  kind: actor
  actor: visitor
  entities:
  - {entity: session, effect: creates, facts: [Device name, Device type, Signed in at, Last active, This device]}
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in'}
  capability: sign-in
---

# Reset the password and sign in

## Trigger

A Visitor cannot sign in because they forgot their password.

## Outcome

The Visitor chose a new password and is signed in with it.
