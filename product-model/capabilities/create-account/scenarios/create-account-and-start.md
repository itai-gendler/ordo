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
- text: The Product checks that the server takes new accounts and does not require email verification
  kind: product
  actor: visitor
  entities:
  - {entity: server, effect: reads, facts: [Sign-ups, Has accounts, Email verification required]}
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
- text: The Product signs the new account in on this device and opens the library
  kind: product
  actor: visitor
  entities:
  - {entity: session, effect: creates, facts: [Device name, Device type, Signed in at, Last active, This device]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-out::create-account'}
---

# Create an account and start reading

## Trigger

A Visitor wants their own library on this server.

## Outcome

The Visitor has a new active account and is signed in on this device.

## Edge cases

- An email that already has an account is refused with "An account with this email already exists."
- The password must be at least 8 characters and typed the same twice.
