<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="Logo/prism-logo-light.png">
    <source media="(prefers-color-scheme: light)" srcset="Logo/prism-logo-dark.jpg">
    <img src="Logo/prism-logo-dark.jpg" width="180" alt="Prism logo">
  </picture>
</p>

<h1 align="center">Prism</h1>

<p align="center">
  Human-in-the-loop AI system for engineering observability, decision explainability,<br />
  validation workflows, and research-oriented market monitoring.
</p>

<p align="center">
  <a href="README.zh-CN.md">中文</a> ·
  <a href="docs/architecture.md">Architecture</a> ·
  <a href="docs/phase3c-validation.md">Phase 3c</a> ·
  <a href="docs/safety-boundaries.md">Safety</a> ·
  <a href="docs/roadmap.md">Roadmap</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Phase-3c%20Shadow-blue" alt="Phase 3c Shadow" />
  <img src="https://img.shields.io/badge/Clean%20Days-0%2F5-orange" alt="Clean Days 0/5" />
  <img src="https://img.shields.io/badge/Mode-Human--in--the--loop-green" alt="Human-in-the-loop" />
  <img src="https://img.shields.io/badge/Validator%20v2-Shadow%20Compare-purple" alt="Validator v2 Shadow Compare" />
  <img src="https://img.shields.io/badge/Trading%20Chain-Protected-red" alt="Trading Chain Protected" />
</p>

---

Prism is a human-in-the-loop AI system for engineering observability, decision explainability, validation workflows, and research-oriented market monitoring.

The project is designed around a simple principle: AI can help organize market signals, validation results, risk context, and operational status, but real trading decisions should remain explainable, auditable, and manually controlled.

## Current status

Prism is currently in **Phase 3c Shadow validation**.

- Current validation progress: `0/5` clean days
- Real trading mode: human-in-the-loop / manual execution
- Validator v2: shadow compare only
- Event intelligence: display-only
- Decision cards: explanation and observability layer
- Production trading chain: not modified by display-only modules

## What Prism does

Prism focuses on:

- Engineering observability for a semi-automatic AI system
- Decision explanation cards for market candidates and holdings
- Phase-based validation workflows
- Runtime and EOD validation visibility
- Source freshness and traceability
- Event intelligence such as earnings, SEC events, sector context, and ETF flow
- Separation between real holdings, virtual holdings, shadow candidates, research-only items, and news-only items

## What Prism does not do

Prism is not positioned as a fully automatic trading bot.

It does not aim to:

- Automatically execute live trades without human confirmation
- Provide financial advice
- Replace risk management or human review
- Treat display-only research signals as trading gates
- Let experimental validators directly affect production clean-day counting

## Frontend views

Prism includes frontend views for engineering status, market overview, research, monitoring, and system health.

Public deployment URLs are intentionally not listed in this repository. Screenshots and selected documentation may be added later after review.

## Repository purpose

This repository is currently used as a public project overview for Prism. It documents the architecture, validation process, safety boundaries, current progress, and roadmap.

Production secrets, broker details, server configuration, private logs, `.env` files, webhooks, account credentials, and sensitive trading data are intentionally excluded.

## Documentation

English:

- [Architecture](docs/architecture.md)
- [Phase 3c Validation](docs/phase3c-validation.md)
- [Decision Cards](docs/decision-card.md)
- [Event Intelligence](docs/event-intelligence.md)
- [Frontend Pages](docs/frontend-pages.md)
- [Safety Boundaries](docs/safety-boundaries.md)
- [Roadmap](docs/roadmap.md)

中文：

- [系统架构](docs/architecture.zh-CN.md)
- [Phase 3c 验证](docs/phase3c-validation.zh-CN.md)
- [Decision Card 决策解释卡](docs/decision-card.zh-CN.md)
- [Event Intelligence 事件情报](docs/event-intelligence.zh-CN.md)
- [前端页面](docs/frontend-pages.zh-CN.md)
- [安全边界](docs/safety-boundaries.zh-CN.md)
- [路线图](docs/roadmap.zh-CN.md)

## Bilingual maintenance policy

English and Chinese documentation should be revised together. When the project status, safety boundary, validation state, or roadmap changes, both language versions should be updated in the same maintenance pass.

## License

License information will be finalized as the public repository matures.

## Disclaimer

This project is for research, engineering observability, and human-in-the-loop decision support. It is not financial advice and should not be used as a basis for live trading without independent review and risk controls.
