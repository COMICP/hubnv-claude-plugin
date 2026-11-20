---
name: hubnv-drafts
description: Make or change HubNV forms and their questions, storefront listings and NV Campaign drafts, or connect the person's own domain to a website. Use when the person asks to build a form, add or edit a listing, plan a campaign, or put their domain on their site.
---

# HubNV drafts

Find the business first: `companies__list`.

**Forms**
1. New form: `forms__create` with the title and its questions. Pass `siteId` to use that website's look.
2. Change one: `forms__read` first for question ids and `draftVersion`, then `forms__update_questions` with every
   change in one `ops` list, passing that `draftVersion`. If it says the form changed, read it again and redo the
   changes.
3. Choice questions take the full list of `options` each time.
4. A live form can be reworded here; it can't lose or retype questions. Changes show once the person publishes
   (`forms__publish`, `confirm: true`).

**Storefront listings**
1. `storefront__create_listing` makes a draft. The description is plain text. Photos are added in HubNV.
2. To edit a draft listing, use `storefront__update_draft_listing` and name only the fields that change.
3. A live listing changes at once. Use `storefront__update_published_listing` with `confirm: true`, only after the
   person agrees to the exact change.

**NV Campaigns**
1. `campaigns__create_draft` with a name and dates (starting tomorrow or later). Add the goal, channels and budget if
   the person gave them.
2. It posts and spends nothing. The person launches it in HubNV.

**Domains**
1. Use `sites__connect_domain` only for a domain the person owns and a site with no domain yet, with `confirm: true`.
2. Give them the returned records to add at their registrar, exactly as returned. Running it again with the same
   domain re-checks it.

Say what was made or changed, with its id. Before asking for a yes, show it: `previews__show` with its kind (`form`,
`listing`, `nvCampaign`) and id. Never publish or make a live change the person didn't ask for.
