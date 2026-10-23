---
date: 2026-10-23
title: "TS-574 DHL Express EU: standardized_product_id removed from shipment create (verified on dev3)"
kb_path: kb/03-workstreams/shipping-easypost/ts-574-dhl-eu-standardized-product-id.md
type: fix-verification
systems: [MPS, EasyPost, DHL Express]
tickets: [TS-574]
status: confirmed
source: slack
---

## Summary
QA (Jiahao Xu) verified the TS-574 core change on the dev3 environment on 2026-10-23 and reported it as passed.

## What was verified
- Test orders (DHL [EXPRESS] via EasyPost): 20011703 (Bonn, Germany) and 20011705 (Berlin, Germany).
- Checked the outbound shipment create request payload at item level:
  - `standardized_product_id` is removed; the field is absent entirely (not sent as null or empty).
  - `code` and `manufacturer_product_id` are kept and populated.
- The channel was confirmed through the EasyPost `carrier_account`.

## Scope note
Verification is on dev3 only. Production rollout status is not covered here; check the Jira board.

## Related
- Slack group DM C0CB34R7VHV, ts 1792749600.718189 (Jiahao to Zephyr Chu, cc Phil Li)
