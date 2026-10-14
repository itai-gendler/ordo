---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Lock folder and enters a 4- or 6-digit PIN, or connects at least 4 dots
  kind: actor
  actor: account-holder
  entities:
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product locks the folder
  kind: product
  actor: account-holder
  entities:
  - {entity: folder, effect: changes, from: Not locked, to: Locked, facts: [Lock type]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Lock a folder with a PIN or pattern

## Trigger

An Account holder prefers a PIN or a pattern to a password.

## Outcome

The folder is locked with the PIN or pattern.
