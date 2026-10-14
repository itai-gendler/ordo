---
kind: primary
routes:
  app: App
steps:
- text: The Account holder opens Active sessions
  kind: actor
  actor: account-holder
  entities:
  - {entity: session, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::active-sessions'}
- text: The Product lists the account's sessions, most recently active first
  kind: product
  actor: account-holder
  entities:
  - {entity: session, effect: reads, facts: [Device name, Device type, Last active, This device]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::active-sessions'}
---

# See the devices signed in

## Trigger

An Account holder wants to know where their account is signed in.

## Outcome

The Account holder sees each signed-in device, with this device marked.
