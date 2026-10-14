---
scope: The ordo server, the Android app and the API contract they share.
method: Static reading of the source and documentation at 0a1ed34e4135; nothing was run.
covered:
- description: Server accounts, sign-in, second step, sessions, profile pictures and mail
  paths:
  - apps/server/src/auth/
- description: Server bookmarks, folders, locks, tags, suggestions, highlights and page fetching
  paths:
  - apps/server/src/bookmarks/
- description: Server import and export
  paths:
  - apps/server/src/import-export/
- description: Server name, owner and public server information
  paths:
  - apps/server/src/server/
- description: Server settings read from the environment
  paths:
  - apps/server/src/config/
  - apps/server/.env.example
- description: Server data shape
  paths:
  - apps/server/prisma/schema.prisma
- description: Shared API contract, schemas and limits
  paths:
  - packages/shared/src/
- description: App screens and routes
  paths:
  - apps/mobile/app/
- description: App feature components for auth, bookmarks, reader, settings and tags
  paths:
  - apps/mobile/src/components/auth/
  - apps/mobile/src/components/bookmarks/
  - apps/mobile/src/components/reader/
  - apps/mobile/src/components/settings/
  - apps/mobile/src/components/tags/
  - apps/mobile/src/components/IncomingShareHandler.tsx
- description: App API client, stores and feature logic
  paths:
  - apps/mobile/src/lib/
  - apps/mobile/src/store/
  - apps/mobile/src/hooks/
exclusions:
- description: Visual design system, theme and shared UI primitives (design, not product behavior)
  paths:
  - apps/mobile/src/theme/
  - apps/mobile/src/components/ui/
  - apps/mobile/assets/
  - docs/material-audit/
- description: Design and animation audits
  paths:
  - docs/ANIMATION-AUDIT.md
  - docs/interaction-polish-audit.md
  - docs/material-3-redesign.md
  - docs/material-comprehensive-audit.md
  - docs/material-performance-follow-up.md
  - docs/material-ui-interactions.md
  - docs/reader-theme-follow-up.md
  - apps/mobile/docs/
- description: 'Server plumbing: HTTP setup, guards, rate limiting, errors and database access'
  paths:
  - apps/server/src/common/
  - apps/server/src/prisma/
  - apps/server/src/main.ts
  - apps/server/src/app.module.ts
- description: Storage encryption of library fields (how data is stored, not what the product does)
  paths:
  - apps/server/src/crypto/
- description: Database migrations
  paths:
  - apps/server/prisma/migrations/
- description: Native Android build plugins and app build configuration
  paths:
  - apps/mobile/plugins/
  - apps/mobile/app.config.js
  - apps/mobile/eas.json
  - apps/mobile/fingerprint.config.js
- description: Tests and test tooling
  paths:
  - apps/server/test/
  - apps/mobile/tests/
- description: Continuous integration and release pipeline
  paths:
  - .github/
  - docs/RELEASES.md
unmapped:
- description: Anonymous install telemetry endpoint and app reporting (peripheral to the bookmark workflows; stated only as a product limitation)
  paths:
  - apps/server/src/telemetry/
  - apps/mobile/src/lib/telemetry.ts
  - apps/mobile/src/lib/telemetry-policy.ts
  - docs/telemetry.md
- description: Operator install, update and uninstall scripts and setup wizard (operator tooling outside the app)
  paths:
  - install.sh
  - scripts/
  - deploy/
  - docs/SERVER-SETUP.md
- description: App self-update, release changelog and About page (app distribution, not library behavior)
  paths:
  - apps/mobile/app/(app)/settings/about.tsx
  - apps/mobile/src/components/settings/ChangelogList.tsx
  - apps/mobile/src/components/NativeUpdateProgress.tsx
  - apps/mobile/src/components/UpdateReadyWatcher.tsx
- description: Copy link, share and open-in-browser actions on bookmarks and highlights (device conveniences)
  paths:
  - apps/mobile/src/lib/copy-link.ts
  - apps/mobile/src/lib/in-app-browser.ts
  - apps/mobile/src/components/browser/
- description: Required authenticator hand-off right after sign-in (a journey across signing in, which the model format cannot express)
  paths:
  - apps/mobile/src/components/auth/MfaEnrollmentScreen.tsx
- description: Offline gate and cached library on the device (connectivity handling)
  paths:
  - apps/mobile/src/components/OfflineGate.tsx
  - apps/mobile/src/lib/query-persist.ts
limitations: []
---

# Coverage
