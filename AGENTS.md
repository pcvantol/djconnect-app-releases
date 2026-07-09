# DJConnect App Releases Agent Instructions

This repository follows the canonical DJConnect design foundation in `pcvantol/djconnect`.

## Role

This repo is a distribution surface for public/community DJConnect app release artifacts and release notes.

It does not own product logic, app source, platform contracts, roadmap or store strategy.

Canonical source files live in `pcvantol/djconnect`:

- `DJCONNECT_CONSTITUTION.md`
- `PRODUCT_VISION.md`
- `PRODUCT_LANGUAGE.md`
- `PLATFORM_GOVERNANCE.md`
- `PLATFORM_QUALITY_STANDARD.md`
- `SYNC_PROMPTS.md`
- `PRODUCT_ROADMAP.md`

## Rules

- Keep artifacts traceable to source commits in app/client source repositories.
- Do not publish signing secrets, certificates, provisioning profiles, tokens or private user data.
- Release notes should be user-facing and use official product language.
- Do not fork roadmap or sync prompts locally.
- App Store/TestFlight planning belongs in canonical distribution/governance documents before release automation changes.
