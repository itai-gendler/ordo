---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Remove photo
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::account'}
- text: The Product deletes the picture
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: changes, facts: [Profile picture]}
  contexts:
    app: {place: 'ordo-app::signed-in::account'}
---

# Remove the profile picture

## Trigger

An Account holder no longer wants a picture on their account.

## Outcome

The account has no picture.
