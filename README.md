# Prism

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

## Public pages

The project currently exposes public read-only views such as:

- Engineering status: `https://heyaaron.asia/engineering`
- Market dashboard: `https://heyaaron.asia/market`
- Research lab: `https://heyaaron.asia/research`
- System status: `https://heyaaron.asia/status`

Some pages or data may be partial, delayed, or intentionally read-only.

## Repository purpose

This repository is currently used as a public project overview for Prism. It documents the architecture, validation process, safety boundaries, current progress, and roadmap.

Production secrets, broker details, server configuration, private logs, `.env` files, webhooks, account credentials, and sensitive trading data are intentionally excluded.

## Documentation

- [Architecture](docs/architecture.md)
- [Phase 3c Validation](docs/phase3c-validation.md)
- [Decision Cards](docs/decision-card.md)
- [Event Intelligence](docs/event-intelligence.md)
- [Frontend Pages](docs/frontend-pages.md)
- [Safety Boundaries](docs/safety-boundaries.md)
- [Roadmap](docs/roadmap.md)

## License

License information will be finalized as the public repository matures.

## Disclaimer

This project is for research, engineering observability, and human-in-the-loop decision support. It is not financial advice and should not be used as a basis for live trading without independent review and risk controls.
