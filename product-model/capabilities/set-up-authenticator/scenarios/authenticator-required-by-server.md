---
kind: primary
routes:
  app: App
steps:
- text: The server requires an authenticator and the account has none
  kind: condition
  actor: account-holder
  entities:
  - {entity: server, effect: reads, facts: [Authenticator required]}
  - {entity: account, effect: reads, facts: [Authenticator]}
  contexts:
    app: {place: 'ordo-app::signed-in::protect-your-account'}
- text: The Product shows Protect your account in place of the library
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::protect-your-account'}
- text: The Account holder adds the key to their authenticator app and enters the code it shows
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::protect-your-account'}
- text: The Product turns the authenticator on, creates ten backup codes and opens the library
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: changes, facts: [Authenticator, Backup codes]}
  contexts:
    app: {place: 'ordo-app::signed-in::protect-your-account'}
---

# Set up an authenticator the server requires

## Trigger

An Account holder without an authenticator signs in to a server that requires one.

## Outcome

The account has an authenticator and the library opens.
