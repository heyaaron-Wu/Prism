# Roadmap

This roadmap describes Prism's public project direction. It intentionally separates documentation, display-only work, validation, and any future production changes.

## Current phase

```text
Phase 3c Shadow validation
Progress: 0/5 clean days
Status: waiting for scheduled EOD validation
```

## Completed or mostly completed

- Service boundary stabilization
- Main frontend pages
- Decision Card explanation layer
- Event Intelligence for earnings, SEC, sector, and ETF context
- Source Trace / Freshness panel
- Phase 3c EOD Viewer
- Runtime P0 failure explanation and audit trail
- Validator v2 schema and shadow compare
- DecisionContext v1 skeleton
- Legacy `ai-trader` cleanup inventory

## Near-term focus

- Wait for the next scheduled EOD
- Observe whether runtime P0/P1 and EOD snapshot both pass
- Keep Phase 3c clean-day logic unchanged
- Keep Validator v2 shadow-only
- Avoid new runtime variables during validation

## Deferred cleanup

Legacy `ai-trader` naming cleanup is deferred.

The accepted cleanup inventory found mostly naming and historical artifacts, not trading-chain risk.

Cleanup should be staged:

1. Documentation-only during Phase 3c
2. Low-risk copy cleanup after stable EOD evidence
3. Operational cleanup only after Phase 3c 5/5 and manual approval
4. Historical reports and backups preserved where useful for auditability

## Future modules

Potential future display-only modules:

- Candidate Lifecycle
- Post-trade Plan
- Entry Setup
- Risk / Reward view
- Validator History
- Source Trace Drilldown

Potential future event layers:

- FDA / PDUFA
- IPO
- Investor Day
- Product Launch
- M&A
- Buyback
- Stock split
- News headline parser

## Not planned during Phase 3c

- Switching active mode
- Replacing the production validator
- Letting Validator v2 affect clean-day counting
- Lowering runtime P0/P1 requirements
- Exposing sensitive production logs
- Adding real execution automation
