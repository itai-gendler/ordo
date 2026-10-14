---
kind: validation
routes:
  app: App
steps:
- text: The Account holder enters a new email and a password
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::email'}
- text: The password does not match the account
  kind: condition
  actor: account-holder
  entities:
  - {entity: account, effect: reads, facts: [Password]}
  contexts:
    app: {place: 'ordo-app::signed-in::email'}
- text: The Product refuses with "Incorrect password."
  kind: product
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::email'}
---

# Wrong current password

## Trigger

An Account holder enters a wrong current password.

## Outcome

Nothing changes and no code is sent.
