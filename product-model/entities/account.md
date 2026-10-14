---
relations:
- entity: folder
  verb: owns
  cardinality: one-to-many
- entity: bookmark
  verb: owns
  cardinality: one-to-many
- entity: tag
  verb: owns
  cardinality: one-to-many
- entity: import
  verb: owns
  cardinality: one-to-many
- entity: session
  verb: owns
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: apps/server/prisma/schema.prisma
- kind: code
  role: implementation
  target: apps/server/src/auth/auth.service.ts#AuthService
---

# Account

A person's account on one server, with the facts that belong to them whatever their role.

## Information kept

- **Display name** — the name shown for the person in the app
- **Email** — the address the person signs in with and receives codes at
- **New email** — an address the person asked to switch to, until they confirm it with the emailed code
- **Password** — the account password, at least 8 characters
- **Email verified** — whether the person confirmed their email with a code
- **Profile picture** — an optional picture shown on the account, resized by the server
- **Authenticator** — whether an authenticator app is set up as a second sign-in step
- **Backup codes** — ten single-use codes that stand in for the authenticator
- **Reader text size** — small, medium, large or extra large
- **Reader typeface** — the reading typeface for articles
- **Reader line spacing** — compact, default or relaxed
- **Reader theme** — system, light or dark
- **Reader AMOLED black** — whether the dark reader uses pure black
- **Member since** — when the account was created

## States

### Active

The account can be signed in to.

### Awaiting email verification

Created on a server that requires email verification and waiting for its emailed code.
