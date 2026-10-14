---
appliesTo:
- type: capability
  id: change-reader-settings
- type: capability
  id: change-appearance-settings
- type: capability
  id: change-controls-settings
references:
- kind: code
  role: implementation
  target: apps/server/src/auth/auth.service.ts#AuthService
- kind: code
  role: implementation
  target: apps/mobile/src/store/settings.ts#useSettingsStore
---

# Reader settings follow the account; appearance and controls stay on the device

Text size, typeface, line spacing and reader theme are kept on the account and apply on every device signed in to it. Appearance and controls settings are kept on each device.
