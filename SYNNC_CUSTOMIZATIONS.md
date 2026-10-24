# Synnc customization changelog

## Upstream

- Project: [OpenWhispr](https://github.com/OpenWhispr/openwhispr)
- Authors: OpenWhispr Team and contributors
- Baseline: `7a6ae826de9ec1caf65f3a6e769475dab2ae829f` (upstream `main`)
- License: [MIT](LICENSE), including Copyright (c) 2024 OpenWhispr Team
- The full history reachable from the upstream baseline is retained. The local `upstream` remote points to the original repository.

## 2026-10-24

- Replaced the authentication welcome subtitle in all 11 existing interface locales with a Synnc Labs customization label and explicit OpenWhispr Team attribution.
- Kept the OpenWhispr welcome title, logo, application identity, and existing behavior intact.
- Added this changelog and a README introduction distinguishing the customization from the upstream application and downloads.

This is a source customization, not a Synnc-authored application or a released binary. No telemetry, credentials, or permissions were added. GitHub Actions is disabled for this private repository to prevent inherited build and release workflows from running automatically.

## Validation

- Passed: upstream `node scripts/check-i18n.js` before and after the customization (using the installed Node v22.11.0).
- Passed: `git diff --check`; JSON parsing and comparison confirming that only `auth.welcomeSubtitle` changed in each of the 11 locale files.
- Passed: byte comparison of all tracked LICENSE/COPYING/NOTICE files against the baseline; original package author retained.
- Not run: full tests, ESLint/Prettier, TypeScript, renderer/native builds, or an app UI smoke test. Dependencies were not installed; upstream requires Node 24 or newer. No app launch, audio recording, or microphone/accessibility permission changes were performed.
