---
kind: primary
routes:
  app: App
steps:
- text: The Account holder opens the bookmark
  kind: actor
  actor: account-holder
  entities:
  - {entity: bookmark, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product opens the link in ordo's browser or the device's browser, as set on this device
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: reads, facts: [Link, Site]}
  - {entity: device-settings, effect: reads, facts: [Open websites in, Force dark mode]}
  contexts:
    app: {place: 'ordo-app::signed-in::reader'}
---

# Open a website

## Trigger

An Account holder opens a bookmark kept as a website.

## Outcome

The page is open in the browser the Account holder chose.
