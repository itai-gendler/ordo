---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Use ordo Cloud under Hosting
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::hosting'}
- text: The Account holder confirms, having been told this server's library is not copied
  kind: actor
  actor: account-holder
  entities:
  - {entity: server, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::hosting'}
- text: The Product signs this device out
  kind: product
  actor: account-holder
  entities:
  - {entity: session, effect: removes}
  contexts:
    app: {place: 'ordo-app::signed-in::hosting'}
- text: The Product keeps ordo Cloud as this device's server and restarts the app at sign-in
  kind: product
  actor: account-holder
  entities:
  - {entity: device-settings, effect: changes, facts: [Server address]}
  - {entity: server, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::hosting'}
---

# Switch to ordo Cloud from Hosting

## Trigger

An Account holder on their own server wants to use ordo Cloud instead.

## Outcome

The device is signed out and the app talks to ordo Cloud.
