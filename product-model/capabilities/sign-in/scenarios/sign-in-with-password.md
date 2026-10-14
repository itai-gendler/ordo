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
- text: The Product checks the password for that account
  kind: product
  actor: visitor
  entities:
  - {entity: account, effect: reads, facts: [Email, Password, Authenticator]}
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in'}
- text: The Product signs this device in and opens the library
  kind: product
  actor: visitor
  entities:
  - {entity: session, effect: creates, facts: [Device name, Device type, Signed in at, Last active, This device]}
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in'}
---

# Sign in with email and password

## Trigger

A Visitor with an active account opens the app.

## Outcome

The device is signed in and shows the library.

## Edge cases

- Signing in on more than 10 devices ends the session the account used least recently.
