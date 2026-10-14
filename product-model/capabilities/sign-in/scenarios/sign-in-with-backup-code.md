---
kind: primary
routes:
  app: App
steps:
- text: The Visitor enters their email and password
  kind: actor
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in'}
- text: The Product asks for the authenticator code
  kind: product
  actor: visitor
  entities:
  - {entity: account, effect: reads, facts: [Authenticator]}
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in-code'}
- text: The Visitor chooses Use a backup code and enters one of their saved codes
  kind: actor
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in-code'}
- text: The Product uses up that backup code
  kind: product
  actor: visitor
  entities:
  - {entity: account, effect: changes, facts: [Backup codes]}
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in-code'}
- text: The Product signs this device in
  kind: product
  actor: visitor
  entities:
  - {entity: session, effect: creates, facts: [Device name, Device type, Signed in at, Last active, This device]}
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in-code'}
---

# Sign in with a backup code

## Trigger

A Visitor whose account has an authenticator cannot reach the authenticator app.

## Outcome

The device is signed in and the backup code used cannot be used again.
