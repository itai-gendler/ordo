---
kind: primary
routes:
  app: App
steps:
- text: The Visitor enters a display name, an email and a password twice
  kind: actor
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::create-account'}
- text: The Product reads that the server requires email verification
  kind: product
  actor: visitor
  entities:
  - {entity: server, effect: reads, facts: [Sign-ups, Has accounts, Email verification required]}
  contexts:
    app: {place: 'ordo-app::signed-out::create-account'}
- text: The Product creates the account waiting for email verification
  kind: product
  actor: visitor
  entities:
  - {entity: account, effect: creates, to: Awaiting email verification, facts: [Display name, Email, Password, Member since]}
  contexts:
    app: {place: 'ordo-app::signed-out::create-account'}
- text: The Product emails a 6-digit code that works for 10 minutes
  kind: product
  actor: visitor
  entities:
  - {entity: account, effect: reads, facts: [Email]}
  contexts:
    app: {place: 'ordo-app::signed-out::create-account'}
- text: The Product opens the code screen for that email
  kind: product
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::verify-email'}
---

# Create an account that waits for its email code

## Trigger

A Visitor creates an account on a server that requires email verification.

## Outcome

The account exists but waits for its emailed code, and the Visitor is on the code screen.

## Edge cases

- When the email already has an account, the Product answers the same way, so the screen never reveals who has an account.
