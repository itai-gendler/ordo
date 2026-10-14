---
domain: library
availability:
- {place: 'ordo-app::signed-in'}
references:
- kind: code
  role: implementation
  target: apps/server/src/bookmarks/bookmarks.service.ts#BookmarksService
- kind: code
  role: implementation
  target: apps/mobile/src/components/bookmarks/ReminderFlow.tsx
- kind: code
  role: implementation
  target: apps/mobile/src/lib/reminder-notifications.ts
- kind: code
  role: implementation
  target: apps/mobile/src/lib/bookmark-reminders.ts#REMINDER_PRESETS
---

# Set reminder

An Account holder asks to be reminded about a bookmark at a set time. The device shows a notification when it comes due.
