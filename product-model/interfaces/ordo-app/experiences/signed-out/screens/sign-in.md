---
entities:
- {entity: server, shows: [Name]}
- {entity: account, collects: [Email, Password]}
- {entity: device-settings, collects: [Server address]}
references:
- kind: code
  role: implementation
  target: apps/mobile/app/(auth)/login.tsx
---

# Sign in

Where a Visitor signs in and sees which server the app talks to, with ways to create an account, reset the password or change server.
