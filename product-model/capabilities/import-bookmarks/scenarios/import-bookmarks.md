---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Import from file under Data and picks a JSON, HTML or CSV file
  kind: actor
  actor: account-holder
  entities:
  - {entity: import, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
- text: The Product starts reading the file
  kind: product
  actor: account-holder
  entities:
  - {entity: import, effect: creates, to: Reading file, facts: [File name]}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
- text: The Product shows how many links are new, already saved or unreadable, and which folders it will create
  kind: product
  actor: account-holder
  entities:
  - {entity: import, effect: changes, from: Reading file, to: Ready, facts: [Format, New bookmarks, Already saved, Skipped rows, New folders, Locked folders]}
  - {entity: folder, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
- text: The Account holder picks Skip, Update or Add copies for links already saved, and confirms Import
  kind: actor
  actor: account-holder
  entities:
  - {entity: import, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
- text: The Product saves the bookmarks
  kind: product
  actor: account-holder
  entities:
  - {entity: import, effect: changes, from: Ready, to: Saving, facts: [Duplicate handling, All at once]}
  - {entity: bookmark, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
- text: The Product creates the folders and tags the file names that the library does not have yet
  kind: product
  actor: account-holder
  entities:
  - {entity: folder, effect: creates, to: Not locked, facts: [Name, Icon, Pinned, Created at]}
  - {entity: tag, effect: creates, facts: [Name, Color]}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
- text: The Product creates the bookmarks, keeping the imported titles and read state
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: creates, to: Fetching, facts: [Link, Title, Description, Author, Published on, Reading time, Folder, Tags, Read, Reading progress, Finished at, Saved at]}
  - {entity: import, effect: changes, from: Saving, to: Complete, facts: [Imported, Updated, Skipped rows]}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
- text: The Product fetches the new bookmarks' pages in the background
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: changes, from: Fetching, to: Article, facts: [Article, Reading time]}
  contexts:
    app: {place: 'ordo-app::signed-in::data'}
---

# Import a bookmarks file

## Trigger

An Account holder brings bookmarks from another service or another ordo server.

## Outcome

The bookmarks and their folders are in the library and their pages are being fetched.

## Edge cases

- A file may be up to 50 MB and 5,000 bookmarks.
- Nested source folders become one folder named with the path, such as Work / Reading.
- Tags named in the file are created when the account does not have them yet.
