---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Turn off authenticator and enters an authenticator or backup code
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::security'}
- text: The Product checks the code
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: reads, facts: [Authenticator, Backup codes]}
  contexts:
    app: {place: 'ordo-app::signed-in::security'}
- text: The Product turns the authenticator off and discards the backup codes
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: changes, facts: [Authenticator, Backup codes]}
  contexts:
    app: {place: 'ordo-app::signed-in::security'}
---

# Turn off the authenticator

## Trigger

An Account holder no longer wants a second sign-in step.

## Outcome

Signing in needs only the password.
