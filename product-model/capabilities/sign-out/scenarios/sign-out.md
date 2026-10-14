---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Sign out in Settings and confirms
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in'}
- text: The Product ends this device's session
  kind: product
  actor: account-holder
  entities:
  - {entity: session, effect: removes}
  contexts:
    app: {place: 'ordo-app::signed-in'}
---

# Sign out of this device

## Trigger

An Account holder is done using ordo on this device.

## Outcome

This device's session has ended and the app shows sign-in.
