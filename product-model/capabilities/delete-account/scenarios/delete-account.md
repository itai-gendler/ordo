---
kind: primary
routes:
  app: App
steps:
- text: The Account holder enters their password, types DELETE MY ACCOUNT and confirms
  kind: actor
  actor: account-holder
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::delete-account'}
- text: The Product checks the password, and the authenticator when one is set up
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: reads, facts: [Password, Authenticator]}
  contexts:
    app: {place: 'ordo-app::signed-in::delete-account'}
- text: The Product deletes the account with its folders, bookmarks, tags and sessions
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: removes, from: Active}
  - {entity: folder, effect: removes, from: Not locked, with: account}
  - {entity: bookmark, effect: removes, from: Article, with: account}
  - {entity: tag, effect: removes, with: account}
  - {entity: session, effect: removes, with: account}
  contexts:
    app: {place: 'ordo-app::signed-in::delete-account'}
- text: The Product says "Account deleted"
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::delete-account'}
---

# Delete the account

## Trigger

An Account holder wants to leave the server and remove their library.

## Outcome

The account and its library are gone and the app shows sign-in.

## Decision points

### Is an authenticator set up?

Does the account have an authenticator?

- Yes → the Account holder also enters an authenticator or backup code, and a used backup code is spent
- No → the password alone is enough
