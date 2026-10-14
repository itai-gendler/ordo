---
kind: primary
routes:
  app: App
steps:
- text: The Visitor asks for a new code
  kind: actor
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::verify-email'}
- text: The Product emails a new 6-digit code to an account still waiting for verification and retires the old one
  kind: product
  actor: visitor
  entities:
  - {entity: account, effect: reads, facts: [Email, Email verified]}
  contexts:
    app: {place: 'ordo-app::signed-out::verify-email'}
---

# Send a new code

## Trigger

A Visitor did not receive the code or let it expire.

## Outcome

A new code is on its way and the old one no longer works.

## Edge cases

- For an address with no waiting account the Product reports the same, and sends nothing.
