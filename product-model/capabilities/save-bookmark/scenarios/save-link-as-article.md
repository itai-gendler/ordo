---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Save bookmark, pastes the link and may pick a folder and tags
  kind: actor
  actor: account-holder
  entities:
  - {entity: bookmark, effect: reads, facts: []}
  - {entity: folder, effect: reads, facts: []}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product saves the bookmark at once with a provisional title from the link
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: creates, to: Fetching, facts: [Link, Title, Site, Folder, Tags, Read, Content kind, Saved at]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product fetches the page in the background and keeps its article
  kind: product
  actor: account-holder
  entities:
  - {entity: bookmark, effect: changes, from: Fetching, to: Article, facts: [Title, Description, Author, Published on, Reading time, Article]}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
- text: The Product suggests up to three of the account's existing tags that match the article
  kind: product
  actor: account-holder
  entities:
  - {entity: tag-suggestion, effect: creates, to: Suggested, facts: [Tag]}
  - {entity: account, effect: reads, facts: []}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-in::library'}
---

# Save a link that becomes an article

## Trigger

An Account holder finds a page they want to read later.

## Outcome

The bookmark is in the library with its article ready to read, and up to three tag suggestions.

## Edge cases

- While links are being fetched the library shows how many of them are done.
- A link that is not an http or https address is refused.
