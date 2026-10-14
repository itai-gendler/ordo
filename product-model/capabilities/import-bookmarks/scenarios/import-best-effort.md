---
kind: primary
routes:
  app: App
steps:
- text: The Account holder turns off All at once and confirms Import
  kind: actor
  actor: account-holder
  entities:
  - {entity: import, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
- text: The Product saves each row it can
  kind: product
  actor: account-holder
  entities:
  - {entity: import, effect: changes, from: Ready, to: Saving, facts: [Duplicate handling, All at once]}
  - {entity: bookmark, effect: creates, to: Fetching, facts: [Link, Title, Folder, Tags, Read, Saved at]}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
- text: The Product reports what was imported and which rows failed and why
  kind: product
  actor: account-holder
  entities:
  - {entity: import, effect: changes, from: Saving, to: Complete, facts: [Imported, Updated, Skipped rows, Failed rows]}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
---

# Keep the rows that succeed

## Trigger

An Account holder turns off All at once under Advanced.

## Outcome

The rows that could be saved are in the library and the rest are listed with reasons.

## Edge cases

- Rows for a locked folder that is not unlocked fail with a reason; the other rows are saved.
