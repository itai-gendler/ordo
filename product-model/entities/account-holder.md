---
kind: person
acts: external
relations:
- entity: account
  verb: has
  cardinality: one-to-one
references:
- kind: code
  role: implementation
  target: apps/server/src/auth/auth.guard.ts#AuthGuard
---

# Account holder

A person signed in to the server with their own account, keeping their own library.
