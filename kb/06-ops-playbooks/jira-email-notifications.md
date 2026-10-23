---
date: 2026-10-23
title: "Jira (jira.casetify.com) email notification default policy"
kb_path: kb/06-ops-playbooks/jira-email-notifications.md
type: process
systems: [Jira]
tickets: []
status: confirmed
source: slack
---

## Summary
Jira issue updates send email notifications by default to the issue's reporter and assignee.

## Rule
- Default policy: any update notifies the reporter and the assignee.
- The policy applies to everyone in Jira (not per-user).
- Notifications are already aggregated: consecutive updates within 10 minutes are bundled into one email, so even very frequent updates produce at most one email every 10 minutes.

## Related
- Slack DM with Skyler Yang (D0BV1B88536), 2026-10-23 17:38–18:11 HKT
