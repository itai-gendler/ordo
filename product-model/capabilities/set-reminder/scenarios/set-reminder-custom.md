---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Custom… and picks a date and time
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product sets the reminder
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: changes, facts: [Reminder]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Remind me at a chosen time

## Trigger

An Account holder wants a reminder at a particular date and time.

## Outcome

The bookmark has a reminder at that time.
