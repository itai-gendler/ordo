---
kind: validation
routes:
  app: App
steps:
- text: The Visitor enters the email and a code
  kind: actor
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::verify-email'}
- text: The code does not match the latest one sent, or it is older than 10 minutes
  kind: condition
  actor: visitor
  entities:
  - {entity: account, effect: reads, facts: [Email verified]}
  contexts:
    app: {place: 'ordo-app::signed-out::verify-email'}
- text: The Product refuses with "This verification code is invalid or has expired."
  kind: product
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::verify-email'}
---

# Wrong or expired code

## Trigger

A Visitor enters a code that does not match or has expired.

## Outcome

The account still waits for verification.

## Edge cases

- After 5 wrong tries the code stops working and a new one must be requested.
