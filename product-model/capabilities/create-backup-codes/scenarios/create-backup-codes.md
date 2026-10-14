---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses New backup codes and enters an authenticator or backup code
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::security'}
- text: The Product replaces every backup code with ten new ones
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: changes, facts: [Backup codes]}
  contexts:
    app: {place: 'ordo-app::signed-in::security'}
- text: The Product shows the new codes once and offers to download them
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: reads, facts: [Backup codes]}
  contexts:
    app: {place: 'ordo-app::signed-in::security'}
---

# Create new backup codes

## Trigger

An Account holder used or lost their backup codes.

## Outcome

Ten new backup codes replace the old ones.
