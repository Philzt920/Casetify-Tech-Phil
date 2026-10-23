# CASETiFY Tech / Phil — Daily ops knowledge base

Daily operation knowledge base for CASETiFY Tech / Phil.

## Note format

One topic per file. Dates are HKT. Do not invent tickets or timelines — record only what is confirmed.

Each note starts with YAML front matter, then:

- **Summary**
- **Rule** (or Rule / decision), when there is one
- **Related**

```yaml
---
date: YYYY-MM-DD
title: Short title
kb_path: kb/.../note.md
type: workstream
systems: []
tickets: []
channels: []
status: confirmed
source: slack
---
```

## Layout

| Path | Purpose |
| --- | --- |
| `kb/00-overview/` | How this KB is organized |
| `kb/01-people-and-channels/` | People and the channels a topic lives in |
| `kb/02-systems/` | Per-system notes |
| `kb/03-workstreams/` | Per-workstream notes |
| `kb/04-tickets/` | Ticket pointers |
| `kb/05-meeting-notes/` | Meeting notes |
| `kb/06-ops-playbooks/` | Repeatable ops playbooks |
| `kb/07-open-questions/` | Unresolved questions |
