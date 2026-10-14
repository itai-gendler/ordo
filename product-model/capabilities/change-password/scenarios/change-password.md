---
kind: primary
routes:
  app: App
steps:
- text: The Account holder enters the current password and a new password twice
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::password'}
- text: The Product checks the current password, and the authenticator when one is set up
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: reads, facts: [Password, Authenticator]}
  contexts:
    app: {place: 'ordo-app::signed-in::password'}
- text: The Product saves the new password
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: changes, facts: [Password]}
  contexts:
    app: {place: 'ordo-app::signed-in::password'}
- text: The Product signs the account out everywhere and starts a new session for this device
  kind: product
  actor: account-holder
  entities:
  - {entity: session, as: old, effect: removes}
  - {entity: session, as: fresh, effect: creates, facts: [Device name, Device type, Signed in at, Last active, This device]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::password'}
- text: The Product says "Password changed. All devices were signed out."
  kind: product
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::password'}
---

# Change the password

## Trigger

An Account holder wants a new password.

## Outcome

The account has the new password; other devices are signed out and this one stays signed in.

## Decision points

### Is an authenticator set up?

Does the account have an authenticator?

- Yes → the Account holder also enters an authenticator or backup code, and a used backup code is spent
- No → the password alone is enough

## Edge cases

- The new password must have at least 8 characters and differ from the current one.
