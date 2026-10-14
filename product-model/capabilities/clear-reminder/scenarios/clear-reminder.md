---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Clear reminder
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product clears the reminder and says "Reminder cleared"
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: changes, facts: [Reminder]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Clear a reminder

## Trigger

An Account holder no longer needs a reminder.

## Outcome

The bookmark has no reminder.
