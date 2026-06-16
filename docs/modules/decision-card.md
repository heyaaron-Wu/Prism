# Decision Cards

Decision Cards are Prism's explanation layer for holdings context, candidate context, research-only items, news-only items, and event-driven context.

They are designed to help a human reviewer understand why an item appears, what context exists, what limitations apply, and whether the information is review-only or potentially action-relevant after independent human review.

## Purpose

Decision Cards provide structured explanations such as:

- why an item appeared,
- which context category it belongs to,
- which blockers or constraints apply,
- which event intelligence signals are relevant,
- whether the item is informational, research-only, shadow-only, or part of a stronger review scope,
- what is missing or stale in the supporting data.

## Scope separation

Prism separates different scopes clearly:

```text
REAL_CONTEXT       real-account or real-position review context
VIRTUAL_CONTEXT    virtual or paper-account review context
SHADOW_CONTEXT     validation-only candidate context
RESEARCH_ONLY      research-only observation
NEWS_ONLY          news or event-only context
DISCOVERED         discovered but not promoted into a stronger scope
```

Public examples use generalized labels rather than real symbols or account-specific items:

```text
EXAMPLE_REAL_CONTEXT
EXAMPLE_VIRTUAL_CONTEXT
EXAMPLE_SHADOW_CANDIDATE
EXAMPLE_RESEARCH_ONLY
EXAMPLE_NEWS_ONLY
```

This keeps the documentation focused on system design instead of private operational state.

## Typical card sections

A Decision Card can include sections such as:

1. Basic identity
2. Scope classification
3. Why it appeared
4. Source trace and freshness
5. Event intelligence, when available
6. Blockers, constraints, or waiting reasons
7. Review notes
8. Risk context placeholder
9. Post-review management placeholder
10. Safety boundary

Not every card needs every section. The goal is to make the available context explicit and avoid implying certainty where evidence is missing.

## Summary and detail modes

Decision Cards can be represented at different levels of detail:

| Mode | Purpose |
| --- | --- |
| Summary | Short, fast view for scanning many items. |
| Full | More complete explanation payload for review. |
| Detail drawer | Expanded view with source, event, blocker, and safety context. |

## Event intelligence integration

Event Intelligence may add display-only context such as:

- earnings timing,
- filing or disclosure context,
- sector-level context,
- ETF-flow context,
- other deferred event candidates.

This information helps explain why something may require attention, but it does not automatically create actionability.

## Safety boundary

Decision Cards are display and explanation tools.

They do not:

- execute trades,
- modify strategy parameters,
- replace validation logic,
- affect validation-day counting,
- promote display-only event intelligence into production gates,
- remove the need for independent human review.

## Public-scope boundary

This document intentionally avoids publishing:

- real account positions,
- private watchlist items,
- account-specific symbols,
- broker-specific order behavior,
- raw runtime payloads,
- private decision logs,
- production execution internals.

The purpose is to document the explanation design, not to expose operational state.
