---
date: 2026-10-24
title: "Production delay email: when it triggers"
kb_path: kb/06-ops-playbooks/production-delay-email-trigger.md
type: process
systems: [production-delay-email]
tickets: []
status: confirmed
source: slack
---

## Summary
How the customer-facing production delay email is triggered, as confirmed by Tech Solution (Gigi Tang, aligned with Tony and Felix) during the iPhone Duo hold/release on 2026-10-23/24.

## Rule
- Orders on hold do not trigger the production delay email.
- After an order is released, release day counts as Day 0; the delay email fires once the order passes release day + production leadtime + 1 day.
- So putting orders on hold is the only order-level way to hold back the email; once released, the email can only be suppressed by stopping the trigger or opting the orders out in code.
- The bulk delay email run happens at 11:00 HKT.

## Related
- #digital-products-team (C04PW678QKC), thread 1792792068.684459, message 1792793736.656039 (Gigi Tang, 2026-10-24 06:15 HKT)
- Context: iPhone Duo hinge-noise steering update (Felix Fong, same thread)
