---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Set up authenticator under Security
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::security'}
- text: The Product shows a new authenticator key for the account, valid for 5 minutes
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: reads, facts: [Email]}
  contexts:
    app: {place: 'ordo-app::signed-in::security'}
- text: The Account holder adds the key to their authenticator app and enters the code it shows
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::security'}
- text: The Product turns the authenticator on and creates ten backup codes
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: changes, facts: [Authenticator, Backup codes]}
  contexts:
    app: {place: 'ordo-app::signed-in::security'}
- text: The Product shows the backup codes once and offers to download them
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: reads, facts: [Backup codes]}
  contexts:
    app: {place: 'ordo-app::signed-in::security'}
---

# Set up an authenticator app

## Trigger

An Account holder wants a second step when signing in.

## Outcome

The account has an authenticator and the Account holder has saved ten backup codes.

## Edge cases

- Replacing an existing authenticator first asks for a current authenticator or backup code.
