---
name: ziply-push-to-ziply
description: Saves content from this conversation to Ziply, as a new draft with its tags, topic link and sources, or as changes to a draft blog or eBook already in Ziply. Use whenever the user asks to save, push, send, upload or store content in Ziply, create a blog, page, eBook or social post in Ziply, or update, overwrite or replace a draft that's in Ziply.
---

# Save content to Ziply

Saving puts the content where the team reviews, approves and publishes it. The save must be accurate: the right record, complete tags, nothing overwritten by mistake, and nothing reported as saved until Ziply confirms it.

## New draft or update?

- **Update** when the user refers to a draft already in Ziply ("update the Pinecone draft", "save this over the original") **and** it's a blog or eBook. Follow *Update a draft* below.
- **New draft** otherwise. Pages and social posts can't be updated from here: offer to save a new draft, or to make the change in Ziply.

## Save a new draft

1. **Assemble what will be saved.**
   - **Content type:** `blog`, `page`, `ebook` or `social`. For a page, its type: Landing Page, Pillar Page (exactly one pillar) or Cluster Page (one pillar and one of that pillar's clusters). For a social post, its channels.
   - **Title**, and for a blog, page or eBook the **body** in Markdown (`bodyFormat: markdown`). An eBook keeps its `### Chapter N: …` headings.
   - **Topic:** the topic ID if the content came from a Ziply topic. Only blogs and social posts can be linked to a topic.
   - **Tags,** by ID from the Ziply tools: pillars and clusters (`list_pillars`), personas (`list_personas`), offerings (`get_brand_profile`), use cases (from the pillars), and the digital twin whose voice was used. Plus journey stage, language and the source links used.
   - **SEO** for a blog or page: meta title, meta description, summary, slug and keywords.
   - **How it was written:** when the write skill's method was used, `contractId` (`blog`, `page` or `ebook`), `knowledgeVersion` (the method version in its `methodology.md`) and `templateId` (the template's key).
   - Ask the user only for **required** values that are missing: the content type, the page type, the channels.
2. **Check what's public.** Ask the user to confirm the content holds no internal figures or quotes from their own buyers, unless they're cleared for publication. Internal documents the user shared count as internal.
3. **Show what will be saved and ask to confirm:** title, type, topic, tags, template, and for a social post each channel with its variants.
4. **Save** with `create_draft`, once. Each call creates a new draft. If it returns an error that names the problem, fix that and retry. If it fails without saying whether the draft was stored (Ziply unavailable or timed out), ask the user to check Content Factory before trying again, so no duplicate is created.
5. **Report the result the tool returned:** the content ID, its status (Draft), and the link to open it in Ziply; for a social post, each channel with its variant numbers. Keep the returned `version` in case the user wants changes. The draft is saved only once the tool has returned it.

## Update a draft

Only **draft** blogs and eBooks can change. In Review and Ready content is refused: offer to save the new version as a new draft, or to make the change in Ziply. Only the title, description, body and (blogs) SEO details can change; tags, topic and status are changed in Ziply.

1. **Find it.** Use the content ID if the conversation has one; otherwise `search_content` with its title or subject, and confirm with the user which one.
2. **Read it** with `get_content` and note its `version`. Before replacing the whole body you need the whole current text: if `truncated` is true, read the rest first (for a long eBook, a few chapters at a time).
3. **Prepare the change.**
   - Send only the fields that change.
   - `body` replaces the whole text. Send the complete new text, never one built from a truncated or partial read.
   - For an eBook, to change some chapters only, send `chapters` (e.g. `{ "from": 3, "to": 4 }`) with a body that is exactly those chapters, each starting with its `### Chapter N: …` heading.
4. **Show the change and ask to confirm:** which fields change, and for the body a summary of what's different (sections added, removed or rewritten, and the word count before and after).
5. **Save** with `update_draft`, passing the `version` from step 2.
   - **Changed since it was read:** someone else edited it. Don't retry blindly: read it again, show the user what changed, and ask how to proceed.
   - **Much shorter:** a body with under half the words it replaces is refused. Explain, and resend with `confirmShorter: true` only if the user says the shorter text is intended.
   - **Not a draft:** it was sent for review or published meanwhile. Offer a new draft instead.
   - **Timed out:** it may or may not have saved. Read it with `get_content` before trying again.
6. **Report the result the tool returned:** the fields changed, the new word count, the new `version` (for any further change) and the link. Search reflects the change once Ziply re-indexes it, usually within minutes.

## When writing isn't possible

If a save says the connection lacks the `content:write` permission, or this assistant can't run write tools, say so plainly, then give a formatted export for the user to paste into Ziply:

```
TITLE: …
TYPE: blog | page (landing, pillar or cluster) | ebook | social
UPDATES: the existing draft's title and link, if this replaces one
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
- Images and video aren't uploaded; they're added in Ziply.

## Structured data

After saving a blog or page, offer JSON-LD for the published page once. Build it only from values Ziply returned or the user gave: the title, meta description and keywords being saved; the publisher's `name`, `legalName`, `url` and social profiles from `get_brand_profile`; an author only if the user confirmed the person. Leave out the URL, dates, images and logo unless the user gives them, never invent any value, and list what was left out. It isn't saved in Ziply; it's for the user's site.

## Don't

- Report success before the tool returns.
- Save or update without the user's confirmation.
- Overwrite a newer version, or send a partial body as the whole.
- Give a readiness score; there isn't one in this release.
- Publish or send for review. This release saves drafts only; publishing happens in Ziply.
