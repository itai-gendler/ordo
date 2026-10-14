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
- text: The Visitor chooses Email me a sign-in code
  kind: actor
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in-code'}
- text: The Product emails a sign-in code to the account's verified email
  kind: product
  actor: visitor
  entities:
  - {entity: account, effect: reads, facts: [Email, Email verified]}
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in-code'}
- text: The Visitor enters the emailed code
  kind: actor
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in-code'}
- text: The Product signs this device in and emails a notice that a sign-in code was used
  kind: product
  actor: visitor
  entities:
  - {entity: session, effect: creates, facts: [Device name, Device type, Signed in at, Last active, This device]}
  - {entity: account, effect: reads, facts: [Email]}
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in-code'}
---

# Sign in with a code sent by email

## Trigger

A Visitor whose account has an authenticator has neither the app nor a backup code.

## Outcome

The device is signed in and the account's email got a notice that an emailed code was used.
