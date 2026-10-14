---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Edit server, or Use your own server, and enters a new address
  kind: actor
  actor: account-holder
  entities:
  - {entity: server, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::hosting'}
- text: The Product checks that the address answers as an ordo server
  kind: product
  actor: account-holder
  entities:
  - {entity: server, effect: reads, facts: [Name, Version]}
  contexts:
    app: {place: 'ordo-app::signed-in::hosting'}
- text: The Account holder confirms Switch server
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
- text: The Product keeps the new address on this device and restarts the app at sign-in
  kind: product
  actor: account-holder
  entities:
  - {entity: device-settings, effect: changes, facts: [Server address]}
  contexts:
    app: {place: 'ordo-app::signed-in::hosting'}
---

# Change the server address from Hosting

## Trigger

An Account holder's server moved to a new address, or they want another server they run.

## Outcome

The device is signed out and the app talks to the new address.
