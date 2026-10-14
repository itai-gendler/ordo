---
appliesTo:
- type: entity
  id: account
  effect: creates
permits:
- actors:
  - visitor
  when:
  - {entity: server, fact: Sign-ups, is: Open}
- actors:
  - visitor
  when:
  - {entity: server, fact: Has accounts, is: 'No'}
references:
- kind: code
  role: implementation
  target: apps/server/src/auth/registration-open.ts#isRegistrationOpen
- kind: code
  role: context
  target: apps/server/.env.example
---

# Visitors create accounts while sign-ups are open, and always the first one

A server takes new accounts while its sign-ups are open. A server with no account yet always takes the first one, so a private server can still be set up.
