---
name: ziply-write-social
description: Writes social posts for the user's company on LinkedIn, X, Facebook, Instagram and YouTube from one idea — for one channel or several at once, with several variants for each — using the brand context and post templates Ziply holds, either as new posts on a topic or by turning a blog post, eBook or page (including one saved in Ziply) into posts that promote it. Use whenever the user asks for a LinkedIn post, a tweet or X post, a Facebook or Instagram post or caption, a YouTube description, social posts for a launch, or to turn content into social posts, even if they don't mention Ziply. Not for personal posts.
---

# Write social posts

One idea becomes posts for one channel or several, with several variants for each, saved to Ziply as **one post grouped by channel**. Social posts aren't pages on the brand's site, so they never get a readiness score.

## When the request just says "post"

If the user asks for a "post" with no channel named and nothing indicating length, ask one question first: *a blog post for your site, or a social post — and if social, which channels?*

## Steps

1. **Resolve the essentials.** The channels (one or more of LinkedIn, X, Facebook, Instagram, YouTube — Reddit too, see below); how many variants per channel (two unless the user says); whose voice — the brand, or a person's digital twin.
2. **The source.** A Ziply topic (`search_topics`, `get_topic_brief`); a blog or eBook already in Ziply (find it with `search_content`, read it with `get_content`); a file from the company's library (a case study, a report or a webinar transcript: `search_library_assets`, then `get_library_asset`, reading every section before using it); or what the user pasted. Pages and social posts already in Ziply can't be loaded from here: ask the user to paste the page, or its key points. For library files follow `ziply-write-ai-ready/references/library.md`: posts quote public files only, and an internal file can shape the angle but its figures and quotes stay out until the user approves them.
3. **The link.** The page the posts promote: the published link the user gives, or the brand's blog. Ziply's `openUrl` opens Content Factory, not the published page, so never use it as the post's link. With no link, the posts carry none — say so.
4. **The user's request.** Their own hashtags, call to action, emoji level, and anything to leave out. These come first.
5. **Voice and context.** `get_brand_profile` for the brand's voice (its brand guideline), restrictions and offerings; `get_digital_twin` for a person's voice; `list_personas` for the audience.
6. **Pick the post type** for each channel from `references/post-types.md`, Ziply's standard post templates (thought leadership, how-to, data share, announcement…), and say which you used. If the user wants their own template from Ziply, ask them to paste it.
7. **Draft.** For each channel, its own variants — written for that channel, differing in angle or opening. Label each `linkedin-v1`, `x-v2` and so on. Stay within each channel's limit: LinkedIn 3,000 characters; X 280 for a standard post (up to 25,000 only if the user asks for a long post); Instagram caption 2,200; YouTube title 100 and description 5,000.
8. **Hand it over,** grouped by channel, saying where the style came from. The user can pick the variants they like. Offer to save them as one post. To save, follow the push skill (`ziply-push-to-ziply`): it asks the user to confirm the content holds no internal figures or buyer quotes, shows what will be saved and waits for a yes, then reports the ID, status and link Ziply returned.

## Who decides style

Emojis, hashtags, link placement and length follow, in order: the user's request, then the person's twin when writing in their voice, then the brand's voice guidance, then the post type's defaults, then the channel's norms, then the house defaults below. Say where the style you applied came from.

**House defaults:** no emoji bullets, no engagement-bait closing questions, no stacks of one-line paragraphs, no hype words, no cliché openings, no blocks of hashtags.

## Reddit as one of the channels

If Reddit is among the channels, write its variants following the Reddit skill's rules, and save them in the same grouped post.

## Instagram and YouTube

This release doesn't create images or video. For Instagram, say what image is needed, and offer the company's own images: `search_library_assets` with `type: image` and no query lists them by name and tag (images aren't searched by meaning); each comes with a `previewUrl`. Instagram captions can't hold a clickable link, so point to the link in bio instead. For YouTube, write from the transcript or notes the user supplies — never describe a video beyond them.

## Always — these never yield to a request or a setting

- No readiness score for social posts.
- No internal figures or quotes from the brand's own buyers in a public post.
- Nothing invented: no statistics, customers, quotes or credentials that aren't real.
- No writing as a named person without their digital twin and the user's confirmation.
- Never use a word in the brand's `prohibitedKeywords`.
- Saving creates a draft. Publishing happens in Ziply.
