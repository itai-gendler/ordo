---
singleton: true
references:
- kind: code
  role: implementation
  target: apps/server/src/config/configuration.ts#loadConfig
- kind: code
  role: implementation
  target: apps/server/src/server/server.service.ts#ServerService
- kind: code
  role: context
  target: apps/server/.env.example
---

# Server

The ordo server the app talks to, with the settings its operator chose and the name its owner gave it.

## Information kept

- **Name** — the server's display name shown in the app; ordo until someone renames it
- **Owner** — the account that owns the server
- **Owner email** — an owner address the operator may configure in place of the first account
- **Sign-ups** — Open or Closed: whether new accounts may be created after the first one
- **Has accounts** — whether any account exists yet
- **Email verification required** — whether new accounts must confirm their email with a code
- **Authenticator required** — whether every account must set up an authenticator app
- **Renaming allowed** — whether the server may be renamed from the app
- **Mail set up** — whether the server sends email; without it one-time codes go to the server log
- **Version** — the server's release version
