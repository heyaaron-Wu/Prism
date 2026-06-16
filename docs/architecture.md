# Prism Architecture

Prism is organized as a layered system that separates observation, explanation, validation, and real-world action.

## Core idea

The system is not designed as a black-box trading bot. It is designed as a human-in-the-loop framework where AI-assisted research, monitoring, and explanation remain separate from real execution.

## High-level layers

```text
Public / UI Layer
  /monitor
  /market
  /research
  /engineering
  /status

Explanation Layer
  Decision Cards
  Event Intelligence
  Source Trace
  Freshness Panel

Validation Layer
  Phase 3c EOD Viewer
  Runtime P0/P1 checks
  Production validator
  Validator v2 shadow compare

Context Layer
  DecisionContext v1 skeleton
  account_context
  candidate_context
  risk_context
  event_context
  freshness_context
  source_trace
  safety_flags

Execution Boundary
  Real actions require manual human execution
  Display-only layers do not reach live execution
```

## Runtime identity

Prism is the canonical project identity.

Some historical artifacts may still contain older `ai-trader` naming, but current runtime identity and project direction are Prism.

The accepted inventory result shows:

- Legacy services are disabled and inactive
- Cron no longer references `ai-trader` paths
- DB schema has no `ai-trader` legacy tables or fields
- Nginx legacy file naming is mainly a historical filename issue
- Remaining identity risk is mostly documentation, frontend copy, metadata, and historical reports

Cleanup is intentionally deferred until after Phase 3c stability.

## Service boundary

The current deployment uses Prism-oriented services such as:

- `prism-backend`
- `prism-worker`
- `prism-bot`
- nginx
- crond

Legacy services such as `ai-trader-backend`, `ai-trader-worker`, and `ai-trader-bot` are expected to remain disabled/inactive unless intentionally reviewed later.

## Safety model

The architecture separates:

- Real holdings
- Virtual or paper holdings
- Shadow candidates
- Research-only items
- News-only items

This distinction prevents explanation and research layers from being mistaken for executable instructions.
