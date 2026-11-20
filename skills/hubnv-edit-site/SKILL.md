---
name: hubnv-edit-site
description: Edit a HubNV website - text, buttons, sections, page titles and search text, theme - as a draft the person reviews, then publish only when they say so. Use when the person asks to change their website.
---

# Editing a HubNV website

1. Find the site: `companies__list`, `sites__list`.
2. Read before writing: `sites__read` for the pages, then `sites__page` for the page you will change. Use the ids it
   returns.
3. Make the smallest edit that does the job:
   - one field: `sites__set_field` (dotted path, e.g. `items.1.answer`)
   - a whole block: `sites__update_block`
   - a new block or section: `sites__insert_block`, `sites__insert_section`
   - a page's title, address or search text: `sites__update_page_meta`
4. Edits land in a draft named "Claude changes". Nothing is live. After editing, read the page again with the draftId
   the edit returned, and tell the person what changed. Show it with `previews__show` (`kind: site`, the site id,
   `draftId`, and `page` for a page other than home).
5. Publish only when the person says to: `sites__publish` with `confirm: true`. If it returns warnings, show them and
   ask; pass `acceptWarnings: true` only if they agree.

If an edit says the site changed since it was read, read it again and redo the change. Never guess ids.
