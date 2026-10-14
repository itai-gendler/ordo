---
kind: edge
routes:
  app: App
steps:
- text: A bookmark's reminder time arrives
  kind: condition
  unattended: true
  entities:
  - {entity: bookmark, effect: reads, facts: [Reminder]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product shows a device notification with the bookmark's title and site, offering Open and Reschedule
  kind: product
  entities:
  - {entity: bookmark, effect: reads, facts: [Title, Site]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# A reminder comes due

## Trigger

A bookmark's reminder time arrives.

## Outcome

The device shows a notification that opens or reschedules the bookmark, and the reminder shows as due.
