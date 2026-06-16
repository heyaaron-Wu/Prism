# Safety Boundaries

Prism is designed around strict separation between observation, explanation, validation, and execution.

## Core boundary

Real trading actions require human review and manual execution.

Display-only modules must not directly change trading behavior.

## Protected components

The following areas should not be modified casually:

- `execute_trade`
- `check_trading_actions`
- `auto_trade` real-account behavior
- `strategy_params`
- `decision_log` write logic
- Recommendation production logic
- Phase 3c clean-day standards
- Production validator role
- Validator v2 counting role

## Phase 3c restrictions

During Phase 3c:

- Do not switch active mode
- Do not manually count clean days
- Do not backfill failed days
- Do not lower runtime P0/P1 standards
- Do not allow Validator v2 to affect clean-day counting
- Do not let display-only Event Intelligence enter trading gates
- Do not make cleanup-only operational changes that introduce unnecessary validation variables

## Display-only modules

The following modules are currently display-only:

- Decision Cards
- Earnings context
- SEC / event risk context
- Sector and ETF flow context
- Source Trace / Freshness panel
- Research lab views

## Data and credential safety

Public repositories should not include:

- `.env` files
- API keys
- Broker credentials
- Webhooks
- Server private configuration
- Database dumps
- Real order logs
- Private account information
- Raw sensitive trading logs

## Disclaimer

Prism is a research, observability, and decision-support project. It is not financial advice and should not be treated as an autonomous live-trading system.
