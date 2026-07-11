# pcvantol/djconnect-app-releases Agent Instructions

## DJConnect Platform Bootstrap

For a clean Codex/AI-agent session in this repository, start here:

`BOOTSTRAP_CODEX_SESSION.md`

That local bootstrap points back to the canonical platform foundation in
`pcvantol/djconnect` and then returns to the repository-specific rules in this
file. This repository extends the DJConnect Platform Foundation. It does not
redefine it.

## Role

This repository owns public app release artifacts, release metadata and localized release/install copy stored in this repository or attached to releases.

It does not own Apple client source, backend contracts, entitlement model or foundation docs.

## Rules

- Keep this repository limited to its repository-specific ownership boundary.
- Do not copy the Platform Foundation, Verification Foundation, Meta
  Engineering Foundation or platform roadmap into this repository.
- Reference `pcvantol/djconnect` for canonical product, architecture,
  governance, verification and release guidance.
- Preserve DJConnect MIT licensing and Spotify trademark/non-affiliation
  language in release or install copy.
- Do not commit secrets, tokens, private keys, production identifiers, raw
  prompts, chat history, raw audio or private release credentials.

Existing local README changes were present before this alignment pass and must not be overwritten by bootstrap work.
