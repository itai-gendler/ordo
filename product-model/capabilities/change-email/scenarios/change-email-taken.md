---
kind: validation
routes:
  app: App
steps:
- text: The Account holder enters a new email and their current password
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::email'}
- text: Another account already uses that email
  kind: condition
  actor: account-holder
  entities:
  - {entity: account, effect: reads, facts: [Email]}
  contexts:
    app: {place: 'ordo-app::signed-in::email'}
- text: The Product refuses with "An account with this email already exists."
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::email'}
---

# The new email already has an account

## Trigger

An Account holder asks to switch to an email another account uses.

## Outcome

Nothing changes and no code is sent.

## Edge cases

- The new email must differ from the current one.
