---
kind: primary
routes:
  app: App
steps:
- text: The Account holder opens the reader controls in an article and picks a text size, typeface, line spacing or theme
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
- text: The Product saves the choice on the account
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: changes, facts: [Reader text size, Reader typeface, Reader line spacing, Reader theme, Reader AMOLED black]}
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
---

# Adjust the reader

## Trigger

An Account holder wants articles bigger, in another typeface or in another theme.

## Outcome

Articles read with the new settings on every device signed in to the account.

## Edge cases

- A new account reads in a medium serif with default spacing and the system theme.
