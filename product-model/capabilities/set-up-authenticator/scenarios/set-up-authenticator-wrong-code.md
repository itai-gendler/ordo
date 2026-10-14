---
kind: validation
routes:
  app: App
steps:
- text: The Account holder enters a code during setup
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::security'}
- text: The code does not match the new key, or setup took longer than 5 minutes
  kind: condition
  actor: account-holder
  entities:
  - {entity: account, effect: reads, facts: [Authenticator]}
  contexts:
    app: {place: 'ordo-app::signed-in::security'}
- text: The Product refuses the code and asks to try again or start setup again
  kind: product
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::security'}
---

# The code does not match

## Trigger

An Account holder enters a code that does not match the new key.

## Outcome

The authenticator stays off.
