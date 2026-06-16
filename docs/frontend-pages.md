# Frontend Pages

Prism includes several public or protected frontend pages for monitoring, research, validation, and system status.

## `/monitor`

The monitoring cockpit is the primary operational view.

Current responsibilities:

- Real holdings overview
- Virtual / paper holdings overview
- Shadow candidates
- Decision Cards
- Detail drawer
- News and event context
- Research layer preview

Current status: mostly stable.

## `/market`

The market dashboard presents broad market, ETF, futures, and sector-style information.

Current status:

- Desktop layout is stable
- Mobile grid issues were addressed
- Numeric overflow and vertical-number layout issues were fixed

## `/research`

The research lab is a research-only page.

It should not be treated as a trading page.

Current status:

- Research-only boundary is clear
- Sector localization issues were addressed
- It does not affect Recommendation production or live execution

## `/engineering`

The engineering page is the main validation and observability page.

It includes:

- Phase 3c validation result viewer
- Runtime gate explanation
- Validator v2 shadow compare display
- Source trace and freshness panel
- Data-source status

The page is publicly accessible for read-only monitoring.

## `/status`

The status page shows service and infrastructure health.

It is useful for checking whether major system components are reachable and stable.

## `/login`

The login page protects formal internal routes where required.

Public read-only pages may be selectively exempted from authentication when intentionally configured that way.

## Frontend strategy

During Phase 3c, frontend changes should remain conservative.

Avoid large layout rewrites or new modules unless they are strictly display-only and do not create new validation variables.
