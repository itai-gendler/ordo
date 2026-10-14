---
kind: validation
routes:
  app: App
steps:
- text: The Account holder enters a password, types the confirmation and confirms
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::delete-account'}
- text: The password does not match
  kind: condition
  actor: account-holder
  entities:
  - {entity: account, effect: reads, facts: [Password]}
  contexts:
    app: {place: 'ordo-app::signed-in::delete-account'}
- text: The Product refuses with "Incorrect password."
  kind: product
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::delete-account'}
---

# Wrong password

## Trigger

An Account holder enters a wrong password when deleting their account.

## Outcome

The account is kept.
