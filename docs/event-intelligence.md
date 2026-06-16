# Event Intelligence

Event Intelligence is Prism's display-only event context layer.

It helps explain why a stock or sector may require attention, but it does not directly modify trading gates or execution logic.

## Current event layers

Prism currently documents and displays structured event intelligence from:

- Earnings events
- SEC filings and event risk
- Sector context
- ETF flow context

## Display-only rule

Event Intelligence is intentionally display-only.

It does not:

- Change live trading gates
- Modify production scoring
- Change Phase 3c validation standards
- Reach `execute_trade`
- Change Recommendation production logic
- Convert research-only items into actionable orders

## Earnings

The earnings layer highlights upcoming or recent earnings timing where available.

Examples of supported context include:

- Today before market open
- After market close
- Days until earnings
- No nearby known earnings event

## SEC and event risk

The SEC layer can display filings or event-risk flags, such as 8-K style events, when available from existing overlay sources.

These are informational warnings and context only.

## Sector and ETF context

Sector and ETF context can help explain broader market or sector conditions around a symbol.

This context is useful for interpretation, but it remains outside the trading gate.

## Future event candidates

Potential future event layers include:

- FDA / PDUFA events
- IPO events
- Investor Day
- Product launches
- M&A events
- Buybacks
- Stock splits
- News headline parsing

These are intentionally deferred until the validation and observability foundation remains stable.
