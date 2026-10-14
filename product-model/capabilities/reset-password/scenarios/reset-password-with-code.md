---
kind: primary
routes:
  app: App
steps:
- text: The Visitor enters their email and chooses Send reset code
  kind: actor
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::reset-password'}
- text: The Product emails a 6-digit reset code when an account has that email
  kind: product
  actor: visitor
  entities:
  - {entity: account, effect: reads, facts: [Email]}
  contexts:
    app: {place: 'ordo-app::signed-out::reset-password'}
- text: The Visitor enters the code and a new password twice
  kind: actor
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::reset-password'}
- text: The Product sets the new password and counts the email as verified
  kind: product
  actor: visitor
  entities:
  - {entity: account, effect: changes, facts: [Password, Email verified]}
  contexts:
    app: {place: 'ordo-app::signed-out::reset-password'}
- text: The Product signs the account out on every device
  kind: product
  actor: visitor
  entities:
  - {entity: session, effect: removes}
  - {entity: account, effect: reads, facts: []}
  contexts:
    app: {place: 'ordo-app::signed-out::reset-password'}
- text: The Product says "Password updated. Sign in with your new password." and opens sign-in
  kind: product
  actor: visitor
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-out::sign-in'}
---

# Reset the password with an emailed code

## Trigger

A Visitor cannot remember their password.

## Outcome

The account has the new password, every device is signed out, and the Visitor is on sign-in with their email filled in.

## Edge cases

- For an email with no account the Product reports the code as sent and sends nothing.
- The Visitor can ask for another code from the code step.
