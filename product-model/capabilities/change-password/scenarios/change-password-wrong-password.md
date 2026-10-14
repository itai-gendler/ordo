---
kind: validation
routes:
  app: App
steps:
- text: The Account holder enters a current password and a new one
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::password'}
- text: The current password does not match
  kind: condition
  actor: account-holder
  entities:
  - {entity: account, effect: reads, facts: [Password]}
  contexts:
    app: {place: 'ordo-app::signed-in::password'}
- text: The Product refuses with "Incorrect password."
  kind: product
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::password'}
---

# Wrong current password

## Trigger

An Account holder enters a wrong current password.

## Outcome

The password is unchanged.
