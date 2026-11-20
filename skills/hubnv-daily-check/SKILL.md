---
name: hubnv-daily-check
description: A short daily or weekly HubNV check-in across the person's businesses, suitable for a scheduled task. Use when the person asks for a regular summary or sets up a recurring check.
---

# Scheduled HubNV check-in

Meant to run on a schedule (Cowork or chat scheduled tasks). Read only.

1. `companies__list`; take the businesses with `access` `available` (or the ones the person named when setting this up).
2. For each, `company__status`.
3. Write one short block per business. Lead with anything that needs action:
   - a site not live
   - a domain or SSL problem
   - new leads since the last check
   - overdue requests
   Then one line saying everything else is fine.

If nothing needs action anywhere, say so in one line. Never edit or publish from a scheduled check.
