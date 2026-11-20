---
name: hubnv-site-status
description: Check how a HubNV business is doing - websites live or not, domains and SSL, forms and recent leads, storefront, open requests and NV Campaigns. Use when the person asks for a status check, a client check-in, or "is my site up".
---

# HubNV status check

1. Call `companies__list`. Use the business the person named; if they named none and there is more than one, ask which.
   Skip any whose `access` is not `available` and say why in one line (`staff_only`: HubNV staff only;
   `not_available`: not open to Claude yet).
2. Call `company__status` with its `company_id`. It covers sites, forms, storefront, requests and campaigns in one call.
3. Only if something needs a closer look:
   - a site not published, or a domain or SSL status that isn't active: `sites__status` with `siteId`
   - traffic: `sites__analytics` (default 30 days)
4. Report in a few lines: what is live, what needs attention, and the next step. Don't list what is fine at length.

Never publish, edit or report problems as part of a status check.
