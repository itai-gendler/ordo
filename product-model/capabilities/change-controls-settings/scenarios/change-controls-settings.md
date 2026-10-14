---
kind: primary
routes:
  app: App
steps:
- text: The Account holder changes the create button's tap or hold action, the share targets, Open websites in or Force dark mode
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::controls'}
- text: The Product keeps the choice on this device
  kind: product
  actor: account-holder
  entities:
  - {entity: device-settings, effect: changes, facts: [Create button tap action, Create button hold action, Quick Bookmark, Show alongside Save, Open websites in, Force dark mode]}
  contexts:
    app: {place: 'ordo-app::signed-in::controls'}
---

# Change the controls

## Trigger

An Account holder wants the app's controls to work differently.

## Outcome

The app uses the new controls on this device.
