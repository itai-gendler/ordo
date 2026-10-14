---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Remind and picks In 1 hour, In 3 hours, Tomorrow or Next week
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product sets the reminder and says when it is set for
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: changes, facts: [Reminder]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Remind me later

## Trigger

An Account holder wants to come back to a bookmark.

## Outcome

The bookmark has a reminder and the device will notify at that time.

## Edge cases

- Choosing a reminder again on a bookmark that has one replaces it.
