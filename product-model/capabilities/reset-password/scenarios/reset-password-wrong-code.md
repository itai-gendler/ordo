---
kind: validation
routes:
  app: App
steps:
- text: The Visitor enters a code and a new password
  kind: actor
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::reset-password'}
- text: The code does not match the latest reset code, or it is older than 10 minutes
  kind: condition
  actor: visitor
  entities:
  - {entity: account, effect: reads, facts: [Email]}
  contexts:
    app: {place: 'ordo-app::signed-out::reset-password'}
- text: The Product refuses with "This verification code is invalid or has expired."
  kind: product
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::reset-password'}
---

# Wrong or expired reset code

## Trigger

A Visitor enters a reset code that does not match or has expired.

## Outcome

The password is unchanged.
