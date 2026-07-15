# Apple Distribution Repository Bootstrap

This repository owns Apple artifact handoff/provenance, not client source or
signing. It adopts AI-Native Engineering Operating System 2.2 from
`pcvantol/djconnect/docs/governance/PLATFORM_ARCHITECT_SYSTEM_INSTRUCTIONS.md`
by reference. Start with synchronized clean main and predecessor verification,
read local records, reconcile `MERGED_UNRECONCILED`, and perform an
implementation-reality check. Lifecycle is `LOCAL_IN_PROGRESS`,
`REVIEWABLE_FROZEN`, `MERGED_UNRECONCILED`, `MERGED_RECONCILED`; cleanup is
fail-closed.
