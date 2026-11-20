---
name: hubnv-leads
description: Read a HubNV business's form responses (leads) - who got in touch, from which page and campaign. Use when the person asks about new leads, enquiries, form submissions or who contacted them.
---

# HubNV leads

1. `companies__list`, then `forms__list` for the business.
2. `forms__responses` with `formId`; newest first. Page on with `before` (the previous page's `nextBefore`) only if the
   person wants older ones.
3. Summarise: how many in the period asked about, and for each the name and contact details, what they asked, and the
   page and source.

Leads are personal data. Show them to the person who asked; don't copy them anywhere else unless they ask.
