---
kind: validation
routes:
  app: App
steps:
- text: The Account holder enters a folder secret
  kind: actor
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::folder'}
- text: The secret does not match the folder's lock
  kind: condition
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: [Lock type]}
  contexts:
    app: {place: 'ordo-app::signed-in::folder'}
- text: The Product refuses with "That password is incorrect."
  kind: product
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::folder'}
---

# Wrong folder password

## Trigger

An Account holder enters a wrong password, PIN or pattern.

## Outcome

The folder stays locked.

## Edge cases

- Repeated wrong tries on a folder are refused for a while.
