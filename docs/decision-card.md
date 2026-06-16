# Decision Cards

Decision Cards are Prism's explanation layer for holdings, candidates, research items, and event-driven context.

They are designed to help a human reviewer understand why an item appears, what state it is in, and what risks or blockers are present.

## Purpose

Decision Cards provide structured explanations such as:

- Why a symbol appeared
- Whether it is a real holding, virtual holding, shadow candidate, research-only item, or news-only item
- Which blockers or constraints apply
- Which event intelligence signals are relevant
- Whether the item is actionable or only informational

## Account and scope separation

Prism separates different scopes clearly:

```text
REAL           real holding or real-account context
VIRTUAL        virtual / paper-account holding
SHADOW         shadow-only validation candidate
RESEARCH_ONLY  research item, not actionable
NEWS_ONLY      news or event-only item, not actionable
DISCOVERED     discovered but not promoted
```

Examples from current project state:

- LLY is treated as a real holding context
- GOOGL is treated as a virtual / paper holding context
- Shadow candidates must not be treated as executable real actions
- Research-only and news-only items must not affect trading gates

## Detail drawer

Decision Card detail view includes sections such as:

1. Basic identity
2. Why it appeared
3. Why it cannot be bought or why it is waiting
4. Entry setup placeholder
5. Risk / reward placeholder
6. Post-trade management placeholder
7. Safety boundary
8. Event intelligence, when applicable

## Current implementation status

Accepted status:

- Backend v1.2 completed
- Summary and full modes completed
- Detail drawer v1 completed
- Raw enums are localized
- Missing fields are handled safely
- Performance optimized from slow self-call behavior to millisecond-level responses

## Boundary

Decision Cards are display and explanation tools.

They do not:

- Execute trades
- Modify strategy parameters
- Replace validation logic
- Affect Phase 3c counting
- Promote display-only event intelligence into gates
