---
kind: primary
routes:
  app: App
steps:
- text: The Account holder changes Design, Theme, Material You colors, AMOLED black, Page transitions or Haptic feedback
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::appearance'}
- text: The Product keeps the choice on this device
  kind: product
  actor: account-holder
  entities:
  - {entity: device-settings, effect: changes, facts: [Design, Theme, Material You colors, AMOLED black, Page transitions, Haptic feedback]}
  contexts:
    app: {place: 'ordo-app::signed-in::appearance'}
---

# Change the app's appearance

## Trigger

An Account holder wants the app to look or move differently.

## Outcome

The app uses the new appearance on this device.
