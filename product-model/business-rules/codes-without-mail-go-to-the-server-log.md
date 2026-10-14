---
appliesTo:
- type: capability
  id: create-account
- type: capability
  id: reset-password
- type: capability
  id: change-email
references:
- kind: code
  role: implementation
  target: apps/server/src/auth/mail.service.ts#MailService
- kind: code
  role: context
  target: apps/server/.env.example
---

# Without mail set up, the server writes one-time codes to its log

A server without mail set up writes one-time codes to its log instead of emailing them. Where the operator requires mail, a code that cannot be emailed fails the request instead.
