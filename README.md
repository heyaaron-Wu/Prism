<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="docs/Logo/prism-logo-light.png">
    <source media="(prefers-color-scheme: light)" srcset="docs/Logo/prism-logo-dark.png">
    <img src="docs/Logo/prism-logo-dark.png" width="180" alt="Prism logo">
  </picture>
</p>

<h1 align="center">Prism</h1>

<p align="center">
  Human-in-the-loop AI system for engineering observability, decision explainability,<br />
  validation workflows, and research-oriented market monitoring.
</p>

<p align="center">
  <a href="README.zh-CN.md">中文</a> ·
  <a href="docs/site/index.html">Static Snapshots</a> ·
  <a href="docs/architecture/architecture.md">Architecture</a> ·
  <a href="docs/validation/phase3c-validation.md">Validation</a> ·
  <a href="docs/governance/safety-boundaries.md">Safety</a> ·
  <a href="docs/governance/roadmap.md">Roadmap</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Human--in--the--loop-AI%20System-blue" alt="Human-in-the-loop AI System" />
  <img src="https://img.shields.io/badge/Focus-Observability-green" alt="Observability" />
  <img src="https://img.shields.io/badge/Focus-Decision%20Explainability-purple" alt="Decision Explainability" />
  <img src="https://img.shields.io/badge/Docs-Bilingual-lightgrey" alt="Bilingual Documentation" />
</p>

---

## Overview

Prism is a documentation-first public overview of a human-in-the-loop AI system for engineering observability, decision explainability, validation workflows, and research-oriented market monitoring.

The project is built around a simple principle: AI can help organize signals, validation results, source context, and operational status, but important decisions should remain explainable, auditable, and manually controlled.

This public repository is intended to explain the project architecture, safety boundaries, modules, and roadmap. Production secrets, private deployment details, account data, server configuration, raw logs, and sensitive operational material are intentionally excluded.

## Why Prism?

AI-assisted systems need more than model output. They need:

- clear system observability,
- traceable decision context,
- validation workflows,
- source freshness checks,
- separation between research, simulation, and real-world review,
- and explicit human oversight before important actions.

Prism explores how these pieces can be organized into a safer and more understandable engineering system.

## Core modules

| Module | Purpose |
| --- | --- |
| Engineering Viewer | Presents validation, source freshness, and system-level observability. |
| Decision Cards | Explains why an item appears, what context exists, and what limitations apply. |
| Event Intelligence | Adds display-only context such as earnings, SEC events, sector signals, and ETF flow. |
| Source Trace | Tracks where information came from and whether the source is fresh enough to trust. |
| Research Lab | Provides a research-only environment for market observation and hypothesis tracking. |
| Safety Boundaries | Keeps display-only information separated from production action paths. |

## Architecture sketch

```mermaid
flowchart TD
    UI[Frontend views] --> Explain[Decision and event context]
    Explain --> Validate[Validation and freshness checks]
    Validate --> Review[Human review boundary]
    Research[Research-only layer] --> Explain
    Sources[Data sources] --> Trace[Source trace and freshness]
    Trace --> Validate
```

## Project focus

Prism focuses on:

- engineering observability for a semi-automatic AI system,
- decision explanation cards for market candidates and holdings,
- phase-based validation workflows,
- runtime and end-of-day validation visibility,
- source freshness and traceability,
- event intelligence such as earnings, SEC events, sector context, and ETF flow,
- separation between real holdings, virtual holdings, shadow candidates, research-only items, and news-only items.

## What Prism does not do

Prism is not positioned as a fully automatic trading bot.

It does not aim to:

- automatically execute live trades without human confirmation,
- provide financial advice,
- replace risk management or human review,
- treat display-only research signals as production gates,
- let experimental validators directly affect production counting or release decisions.

## Static frontend snapshots

Public-safe static snapshots of the Prism frontend are available under [`docs/site/`](docs/site/index.html):

- [Engineering snapshot](docs/site/engineering.html)
- [Market snapshot](docs/site/market.html)
- [Monitor snapshot](docs/site/monitor.html)
- [Research snapshot](docs/site/research.html)

These pages are static, sanitized snapshots. They do not connect to live Prism services, broker accounts, private APIs, raw logs, or production systems.

## Repository scope

This repository is currently documentation-first. Source code and additional artifacts may be published gradually after security, privacy, and operational review.

Excluded from this repository:

- production secrets,
- broker details,
- server configuration,
- private logs,
- `.env` files,
- webhooks,
- account credentials,
- sensitive trading or operational data.

## Documentation

Architecture:

- [Architecture](docs/architecture/architecture.md)
- [系统架构](docs/architecture/architecture.zh-CN.md)

Validation:

- [Phase 3c Validation](docs/validation/phase3c-validation.md)
- [Phase 3c 验证](docs/validation/phase3c-validation.zh-CN.md)

Modules:

- [Decision Cards](docs/modules/decision-card.md)
- [Decision Card 决策解释卡](docs/modules/decision-card.zh-CN.md)
- [Event Intelligence](docs/modules/event-intelligence.md)
- [Event Intelligence 事件情报](docs/modules/event-intelligence.zh-CN.md)
- [Frontend Pages](docs/modules/frontend-pages.md)
- [前端页面](docs/modules/frontend-pages.zh-CN.md)

Governance:

- [Safety Boundaries](docs/governance/safety-boundaries.md)
- [安全边界](docs/governance/safety-boundaries.zh-CN.md)
- [Roadmap](docs/governance/roadmap.md)
- [路线图](docs/governance/roadmap.zh-CN.md)

## Bilingual maintenance policy

English and Chinese documentation should be revised together. When the project scope, safety boundary, validation design, or roadmap changes, both language versions should be updated in the same maintenance pass.

## License

License information will be finalized as the public repository matures.

## Disclaimer

This project is for research, engineering observability, and human-in-the-loop decision support. It is not financial advice and should not be used as a basis for live trading without independent review and risk controls.
