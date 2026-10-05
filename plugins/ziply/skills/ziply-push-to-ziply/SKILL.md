---
name: ziply-push-to-ziply
description: Saves content from this conversation to Ziply as a new draft, with its tags, topic link and sources. Use whenever the user asks to save, push, send, upload or store content in Ziply, create a blog, page, eBook or social post in Ziply, or update a draft that's in Ziply.
---

# Save content to Ziply

Saving puts the content where the team reviews, approves and publishes it. The save must be accurate: the right content type, complete tags, and nothing reported as saved until Ziply confirms it.

## Steps

1. **New drafts only.** This release saves new drafts; it can't update a draft that's already in Ziply. If the user refers to existing content ("update the Pinecone draft"), say so, and offer to save this version as a new draft or to make the change in Ziply.
2. **Assemble what will be saved.**
   - **Content type:** `blog`, `page`, `ebook` or `social`. For a page, its type: a Landing Page, a Pillar Page (exactly one pillar) or a Cluster Page (one pillar and one of that pillar's clusters). For a social post, its channels.
   - **Title**, and for a blog, page or eBook the **body** (Markdown) with `bodyFormat: markdown`.
   - **Topic:** the topic ID if the content came from a Ziply topic. Only blogs and social posts can be linked to a topic.
   - **Tags,** by ID from the Ziply tools: pillars and clusters (`list_pillars`), personas (`list_personas`), offerings (`get_brand_profile`), use cases (from the pillars), and the digital twin whose voice was used. Plus journey stage, language and the source links used.
   - **SEO** for a blog or page: meta title, meta description, summary, slug and keywords.
   - Ask the user only for **required** values that are missing: the content type, the page type, the channels.
3. **Check what's public.** Ask the user to confirm the content holds no internal figures or quotes from their own buyers, unless they're cleared for publication. Internal documents the user shared count as internal.
4. **Show what will be saved and ask to confirm:** title, type, topic, tags, and for a social post each channel with its variants.
5. **Save** with `create_draft`, once. Each call creates a new draft. If it returns an error that names the problem, fix that and retry. If it fails without saying whether the draft was stored (Ziply unavailable), ask the user to check Content Factory before trying again, so no duplicate is created.
6. **Report the result the tool returned:** the content ID, its status (Draft) and the link to open it in Ziply; for a social post, each channel with its variant numbers. The draft is saved only once the tool has returned it. Until then, don't say "saved". There's no readiness score in this release; don't give one.

## When writing isn't possible

If `create_draft` says the connection lacks the `content:write` permission, or this assistant can't run write tools, say so plainly, then give a formatted export for the user to paste into Ziply:

```
TITLE: …
TYPE: blog | page (landing, pillar or cluster) | ebook | social
CHANNELS: for each channel — its variants (<channel>-v1, -v2…)
REDDIT: subreddit, title and flair for each Reddit variant
LINK: the page the post promotes, or none
TOPIC: … (topic ID, if any)
META TITLE: …
META DESCRIPTION: …
SOURCES:
- URL
BODY:
…
```

Never imply the draft was saved when it wasn't.

## Social posts, including Reddit

- **One post per idea, grouped by channel.** Save the post once, with each channel's variants (`linkedin-v1`, `x-v2`…) and an optional name for each. Each channel appears once.
- **Channels:** LinkedIn, X, Facebook, Instagram, YouTube and Reddit. Facebook and Instagram take a caption and a type (Post, Reel or Story); YouTube a title and description; Reddit a title and body, or a link for a link post.
- **The link goes in the post text**, where the channel allows it.
- **Reddit:** Ziply doesn't store the subreddit or flair yet; tell the user to set them when publishing from Ziply.
- **No readiness score** for social posts.
- Images and video aren't uploaded; they're added in Ziply.

## Don't

- Report success before the tool returns.
- Save without the user's confirmation.
- Publish. This release saves drafts only, and publishing happens in Ziply.
