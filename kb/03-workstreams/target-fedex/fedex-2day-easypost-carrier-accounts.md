---
date: 2026-10-20
title: FedEx 2Day EasyPost — always set CASETiFY carrier account
kb_path: kb/03-workstreams/target-fedex/fedex-2day-easypost-carrier-accounts.md
type: workstream
systems: [shipping-easypost]
tickets: [TS-563]
channels: [#target-usa]
status: confirmed
source: slack
---

# FedEx 2Day + EasyPost: always set CASETiFY carrier account

## Summary
For FedEx 2Day via EasyPost, an empty `carrier_accounts` list let EasyPost pick Target’s cheapest FedEx 2Day rate. The fix always attaches a CASETiFY FedEx 2Day carrier account so non-DVS (own ecom) orders are not billed to Target.

## Context
Target DVS FedEx account misuse reported in #target-usa (related ticket TS-563).

## Rule / decision
Always set a CASETiFY FedEx 2Day carrier account by process location:
- `us_ws` → US West carrier account
- otherwise → US carrier account

Previously accounts were only attached when process location was `us` or `us_ws`; **HK** (and other locations) sent `carrier_accounts: []`.

## What happened
- **2026-10-20 ~5:44 PM HKT** — fix deployed
- Live test order **#33975738**: request included `ca_d0147ecd94f745a987a42ceeb95cb64b` (FedEx 2Day); charge did **not** hit Target
- Broken sample before: `carrier_accounts: []`

## Related
- Ticket: TS-563
- Channel: #target-usa
- Scope: FedEx 2Day EasyPost path only; other carriers/services need their own check if similar empty-account behavior exists
