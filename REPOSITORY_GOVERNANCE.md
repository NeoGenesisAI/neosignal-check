# Repository Governance Contract

Policy ID: `ng-repo-governance/1.0.0`
Last reviewed: 2026-08-27

## Identity

- Repository: `Yesol-Pilot/neosignal-check`
- Lifecycle class: `service-verification-surface`
- Current owner: `Yesol-Pilot`
- Intended owner: `NeoGenesisAI`
- Canonical branch: `main`
- Visibility: `public`
- Production status: `UNKNOWN`
- Transfer state: `REQUIRED`

`UNKNOWN` means not independently verified and must never be reported as PASS.

## Purpose and current risk

NeoSignal Check is a public company signal or verification surface. Signals can influence operational, product, or public decisions, so definitions, sources, freshness, uncertainty, and failure behavior must be explicit.

- Active sources, calculation definitions, schedules, consumers, hosting, freshness, false-positive and false-negative treatment, and rollback remain `UNKNOWN`.
- Missing or unreadable input must not collapse into a healthy zero or PASS.
- A status page or JSON endpoint must bind the observed result to source and computation identity, not merely serve a caller-authored value.
- Public output must redact credentials, private repository data, personal identifiers, and internal paths.

## Required remediation

- [ ] Document each signal, source, calculation, unit, freshness, expected range, unavailable state, consumer, and action boundary.
- [ ] Run full-history secret, dependency, license, public-claim, sample-data, and scheduled-job audits.
- [ ] Add schema, source-unavailable, stale, malformed, duplicate, range, clock, calculation, redaction, endpoint, cache, monitoring, and rollback tests.
- [ ] Separate signal producer, deterministic verifier, publisher, and consumer decision authority.
- [ ] Bind public status to exact source revision, calculation revision, timestamp, result, limitations, and health state.
- [ ] Transfer the repository to `NeoGenesisAI` while preserving public URLs and monitoring integrations.

## Pull-request and branch rules

- One task, one branch, one isolated worktree.
- Draft inactivity limit: 14 days; maximum stack depth: 3.
- Ready WIP limit: 5; Draft WIP limit: 10.
- PRs declare signal definition, source, freshness, consumer, public output, migration, and rollback impact.
- Review conversations resolve before squash merge.
- `main` is not force-pushed or deleted.

## Exit criteria

The repository becomes `TRANSFERRED_COMPLIANT` only when organization ownership, explicit signal contracts, fail-closed unavailable states, source and calculation lineage, public privacy, endpoint monitoring, consumer boundaries, and rollback are proven.

The presence of this file alone is not compliance.
