---
appliesTo:
- type: capability
  id: read-bookmark
- type: capability
  id: set-reminder
- type: capability
  id: clear-reminder
references:
- kind: code
  role: implementation
  target: packages/shared/src/reminders.ts#reminderStatus
- kind: code
  role: implementation
  target: apps/mobile/src/lib/bookmark-reminders.ts#reminderClearsOnOpen
---

# A due reminder stays due until it is cleared or its bookmark is opened

A reminder whose time has passed shows as due, and the device notifies once. Opening the bookmark, or clearing the reminder, removes it; opening a bookmark whose reminder is still upcoming keeps the reminder.
