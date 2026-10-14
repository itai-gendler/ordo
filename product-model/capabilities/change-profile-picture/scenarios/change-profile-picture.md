---
kind: primary
routes:
  app: App
steps:
- text: The Account holder chooses Choose photo or Take photo and picks an image
  kind: actor
  actor: account-holder
  entities: []
  contexts:
    app: {place: 'ordo-app::signed-in::account'}
- text: The Product resizes the image and keeps it as the profile picture
  kind: product
  actor: account-holder
  entities:
  - {entity: account, effect: changes, facts: [Profile picture]}
  contexts:
    app: {place: 'ordo-app::signed-in::account'}
---

# Set a profile picture

## Trigger

An Account holder wants a picture on their account.

## Outcome

The account shows the new picture.

## Edge cases

- JPEG, PNG and WebP images are accepted up to the size the server allows (2 MB unless the operator changes it).
- Animated images are accepted only where the operator allows them.
