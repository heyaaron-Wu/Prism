# Phase 3c Validation

Phase 3c is Prism's current shadow validation phase.

The goal is to observe whether the system can pass a full validation day under strict production-style conditions before any later phase is considered.

## Current status

```text
Phase: 3c Shadow
Clean day progress: 0/5
Phase 3d: locked
Manual clean-day backfill: not allowed
```

## Clean-day requirements

A clean day requires more than an end-of-day snapshot pass.

The system must satisfy:

- Scheduled EOD run is valid
- Full-day coverage is valid
- Coverage threshold is accepted
- EOD snapshot P0/P1/P2 passes
- Runtime shadow P0/P1 passes for the full day
- Dedupe guard does not skip the day
- Manual runs are not counted

## Important distinction

```text
EOD Snapshot PASS does not automatically mean Clean Day PASS.
```

A prior validation result showed:

```text
EOD Snapshot: P0/P1/P2 PASS
Full Day Coverage: 98.7%
Day Counted: NO
failed_conditions = [shadow_runtime_p0_all_pass=false]
runtime_p0_fail_count = 99
```

This means the day was not counted because all-day runtime shadow validation did not fully pass.

## Runtime P0 audit result

A runtime P0 failure explorer reviewed the 99 P0 records.

Accepted conclusion:

- 99 runtime P0 records were located and verified
- All were the same mismatch type: `V1阻断V2放行`
- The failures were concentrated around 14:31–16:20 UTC
- The raw FAIL lines lacked symbol payload
- Later PASS logs from 16:24 UTC showed VZ / HSBC pending-order account blocker alignment
- `v2_actionable_orders=[]`
- No real V2 actionable release was found
- No display-only feature contamination was found
- Primary root cause: older runtime account-blocker alignment and insufficient log payload

## Validator v2 role

Validator v2 is currently used only as a shadow compare layer.

It does not:

- Replace the production validator
- Affect clean-day counting
- Override production Phase 3c rules
- Allow a day to be counted simply because v2 passes

## Current strategy

The current strategy is to wait for the next scheduled EOD and observe whether both the EOD snapshot and all-day runtime shadow gate pass.

No manual clean-day backfill should be performed.
