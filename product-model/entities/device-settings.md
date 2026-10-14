---
references:
- kind: code
  role: implementation
  target: apps/mobile/src/store/settings.ts#useSettingsStore
---

# Device settings

The settings the app keeps on one device rather than on the account: which server it talks to, how it looks, and how its controls behave.

## Information kept

- **Server address** — the ordo server the app talks to: ordo Cloud by default, or a server the person runs
- **Design** — Standard or Expressive
- **Theme** — system, light or dark
- **Material You colors** — whether the app takes its colors from the device
- **AMOLED black** — whether dark surfaces use pure black
- **Page transitions** — how screens animate
- **Haptic feedback** — whether actions vibrate
- **Create button tap action** — what tapping the create button does
- **Create button hold action** — what pressing and holding the create button does
- **Quick Bookmark** — whether sharing a link to ordo saves it straight away
- **Show alongside Save** — whether Quick Bookmark appears next to the regular Save share target
- **Open websites in** — ordo's own browser or the device's browser
- **Force dark mode** — whether websites are darkened in ordo's browser
