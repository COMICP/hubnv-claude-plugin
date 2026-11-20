---
name: hubnv-posts
description: Draft, preview and schedule a HubNV business's Facebook and Instagram posts. Use when the person asks to write, plan or schedule social posts, including on a recurring task.
---

# HubNV social posts

1. Find the business: `companies__list`. Check where it can post: `socials__destinations`.
2. For photos, search the library: `library__search` with `type: image`. Use the returned ids as `media`.
3. `socials__create_draft_post` with the caption, destinations, media and a planned time (`whenToPostUtc`, ISO 8601 UTC).
   An Instagram post with 2 or more images needs `instagramAspect`.
4. Show it before asking. The draft comes back with its picture (or, when there isn't one, its own photos) and its
   review link; give the person both. `previews__show` with `kind: socialPost` shows it again later.
5. To change it, `socials__update_draft_post` with only the fields that change, then show it again.
6. Schedule only after the person agrees to that post and time: `socials__schedule_post` with `confirm: true`.

On a scheduled task, draft and preview only. Leave scheduling to the person unless they asked for it when setting the
task up. A post with a boost is scheduled in HubNV. Never schedule a post the person hasn't seen.
