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
- text: The Product finds an authenticator on the account and asks for its code
  kind: product
  actor: visitor
  entities:
  - {entity: account, effect: reads, facts: [Authenticator]}
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in-code'}
- text: The Visitor enters the 6-digit code from their authenticator app
  kind: actor
  actor: visitor
  entities: []
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

# Sign in with an authenticator code

## Trigger

A Visitor whose account has an authenticator signs in.

## Outcome

The device is signed in after the second step.

## Edge cases

- The second step must be finished within 5 minutes and allows 5 wrong codes.
