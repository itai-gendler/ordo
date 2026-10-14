---
kind: primary
routes:
  app: App
steps:
- text: The Account holder enters the new email and their current password and chooses Send code
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::email'}
- text: The Product checks the password, and the authenticator when one is set up
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: reads, facts: [Password, Authenticator]}
  contexts:
    app: {place: 'ordo-app::signed-in::email'}
- text: The Product keeps the new address as pending and emails it a 6-digit code
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: changes, facts: [New email]}
  contexts:
    app: {place: 'ordo-app::signed-in::email'}
- text: The Product emails the current address a notice about the requested change
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: reads, facts: [Email, New email]}
  contexts:
    app: {place: 'ordo-app::signed-in::email'}
- text: The Account holder enters the code on Verify new email
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::email'}
- text: The Product switches the account to the new, verified email
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: changes, facts: [Email, New email, Email verified]}
  contexts:
    app: {place: 'ordo-app::signed-in::email'}
- text: The Product emails the previous address that the email changed and returns to Settings
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: reads, facts: [Email]}
  contexts:
    app: {place: 'ordo-app::signed-in::email'}
---

# Change the email and confirm it

## Trigger

An Account holder wants to sign in and get mail at a new address.

## Outcome

The account uses the new, verified email and the old address got a notice.

## Decision points

### Is an authenticator set up?

Does the account have an authenticator?

- Yes → the Account holder also enters an authenticator or backup code, and a used backup code is spent
- No → the password alone is enough

## Edge cases

- The Account holder can ask for a new code from the confirm step.
- A wrong or expired code is refused; the account keeps its current email.
