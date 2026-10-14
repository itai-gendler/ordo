---
kind: primary
routes:
  app: App
steps:
- text: The Account holder enters a new display name and chooses Save
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::display-name'}
- text: The Product saves the name
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: changes, facts: [Display name]}
  contexts:
    app: {place: 'ordo-app::signed-in::display-name'}
---

# Change the display name

## Trigger

An Account holder wants a different name on their account.

## Outcome

The account shows the new name.

## Edge cases

- A display name must have 1 to 64 characters.
