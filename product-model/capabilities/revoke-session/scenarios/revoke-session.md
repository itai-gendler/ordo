---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Revoke on a session and confirms
  kind: actor
  actor: account-holder
  entities:
  - {entity: session, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::active-sessions'}
- text: The Product ends that session
  kind: product
  actor: account-holder
  entities:
  - {entity: session, effect: removes}
  contexts:
    app: {place: 'ordo-app::signed-in::active-sessions'}
---

# Revoke another device's session

## Trigger

An Account holder sees a device that should no longer be signed in.

## Outcome

That device is signed out.
