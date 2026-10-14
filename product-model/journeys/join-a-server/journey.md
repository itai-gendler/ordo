---
actors:
- visitor
references:
- kind: code
  role: implementation
  target: apps/mobile/app/(auth)/register.tsx
- kind: code
  role: implementation
  target: apps/mobile/app/(auth)/verify-email.tsx
---

# Join a server

## Goal

A person without an account on a server that requires email verification ends up signed in to their new account.

## Success criterion

The new account's email is verified and the device is signed in to it.
