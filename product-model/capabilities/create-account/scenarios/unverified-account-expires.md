---
kind: edge
routes:
  app: App
steps:
- text: An account waits for email verification and its latest code expired more than a moment ago
  kind: condition
  unattended: true
  entities:
  - {entity: account, effect: reads, facts: [Email verified]}
  contexts:
    app: {place: 'ordo-app::signed-out::verify-email'}
- text: The Product removes the unconfirmed account
  kind: product
  entities:
  - {entity: account, effect: removes, from: Awaiting email verification}
  contexts:
    app: {place: 'ordo-app::signed-out::verify-email'}
---

# An unconfirmed account expires

## Trigger

An account waiting for email verification is left unconfirmed.

## Outcome

The unconfirmed account is gone, and its email can be used to sign up again.

## Edge cases

- Asking for a new code replaces the old one and starts another 10 minutes.
