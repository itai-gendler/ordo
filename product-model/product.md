---
id: ordo
summary: 'A self-hostable bookmark manager: save a link, read the article, and keep it, on ordo Cloud or a server you run.'
category: bookmark-manager
tags:
- bookmarks
- read-later
- self-hosted
- reader
authors:
- name: Axolet Labs
  url: https://github.com/axoletlabs
license: AGPL-3.0-only
languages:
- en
limitations:
- Each account's library is private to that account; nothing is shared between accounts.
- Libraries stay on the server they were saved to; switching between ordo Cloud and a server you run copies nothing.
- People sign in with an email address and password; there is no sign-in through another provider.
- Exports carry bookmark details, never the saved article text.
- The app sends ordo Cloud only anonymous daily counts; a server you host receives none.
references:
- kind: doc
  role: intent
  target: README.md
- kind: doc
  role: context
  target: docs/SERVER-SETUP.md
- kind: doc
  role: context
  target: docs/telemetry.md
---

# ordo

ordo is a bookmark manager. People save links from the Android app, or by sharing them from other apps; the server fetches each
page and keeps a clean article to read in the app, or keeps the link as a website when the page is not an article. Bookmarks are
filed in folders, labelled with tags, highlighted while reading, and brought back with reminders. Folders can be locked so their
bookmarks stay out of sight until unlocked. New installs use ordo Cloud, run by Axolet; anyone can instead run their own ordo
server and point the app at it.

## Intent

"A bookmark manager. Save a link, read the article, and keep it." The server is optional: whoever hosts one keeps it online,
updated and backed up, and Axolet does not operate a server someone else hosts.
