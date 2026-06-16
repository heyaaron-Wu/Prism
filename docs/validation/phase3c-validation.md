# Phase 3c Validation Design

Phase 3c is described here as a shadow-validation design pattern inside Prism. The public documentation focuses on validation concepts and safety boundaries rather than private runtime counters, current clean-day progress, raw logs, or operational incident details.

## Purpose

Phase-style validation is used to prevent an AI-assisted system from moving too quickly from observation into stronger operational confidence.

The goal is to evaluate whether the system can maintain a full validation day under strict, production-style conditions while keeping experimental or display-only components outside production authority.

## Clean-day concept

A clean day is not simply an end-of-day status message. It is a stricter acceptance concept that requires multiple conditions to hold across the validation window.

A public-safe clean-day design may include checks such as:

- scheduled validation run was valid,
- full-day coverage was valid,
- required coverage threshold was met,
- end-of-day snapshot passed required severity checks,
- runtime shadow checks passed across the validation window,
- deduplication guard did not skip or double-count the day,
- manual runs were not treated as scheduled validation evidence.

## Important distinction

```text
EOD Snapshot PASS does not automatically mean Clean Day PASS.
```

An end-of-day snapshot can show that a final state looks acceptable, while a stricter clean-day gate may still fail because a runtime condition did not hold across the full validation window.

This distinction is important because Prism treats validation as an auditable process, not a single final message.

## Runtime gate design

Runtime validation exists to detect problems that may not be visible in a final end-of-day snapshot.

Examples of runtime-gate concepts include:

- production-versus-shadow decision alignment,
- blocker consistency,
- stale-source handling,
- missing-payload detection,
- actionability checks,
- display-only contamination checks,
- validation trace completeness.

Public documentation describes these concepts at a design level. It does not publish private runtime failure counts, raw failure lines, internal symbols, or operational incident payloads.

## Validator v2 role

Validator v2 is treated as a shadow-compare layer in the public design.

It does not:

- replace the production validator,
- weaken production validation rules,
- directly count a validation day,
- override production safety boundaries,
- turn research-only or display-only information into production gates.

## Manual-run policy

Manual runs can be useful for debugging and inspection, but they should not be counted as scheduled validation evidence.

This prevents accidental backfilling, duplicate counting, or validation results that are not comparable with scheduled runs.

## Public-scope boundary

This document intentionally avoids publishing:

- current clean-day progress,
- raw validation failure counts,
- private runtime logs,
- production symbols or account details,
- internal server paths,
- broker-specific behavior,
- private validator payloads.

The purpose of this file is to explain the validation design, not to serve as a live operations report.
