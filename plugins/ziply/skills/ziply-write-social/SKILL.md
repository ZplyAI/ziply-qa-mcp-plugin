---
name: ziply-write-social
description: Writes social posts for the user's company on LinkedIn, X, Facebook, Instagram and YouTube from one idea — for one channel or several at once, with several variants for each — using the brand context Ziply holds, either as new posts on a topic or by turning an existing blog post or page into posts that promote it. Use whenever the user asks for a LinkedIn post, a tweet or X post, a Facebook or Instagram post or caption, a YouTube description, social posts for a launch, or to turn content into social posts, even if they don't mention Ziply. Not for personal posts.
---

# Write social posts

One idea becomes posts for one channel or several, with several variants for each, saved to Ziply as **one post grouped by channel**. Social posts aren't pages on the brand's site, so they never get a readiness score.

## When the request just says "post"

If the user asks for a "post" with no channel named and nothing indicating length, ask one question first: *a blog post for your site, or a social post — and if social, which channels?*

## Steps

1. **Resolve the essentials.** The channels (one or more of LinkedIn, X, Facebook, Instagram, YouTube — Reddit too, see below); how many variants per channel (two unless the user says); whose voice — the brand, or a person's digital twin.
2. **The source.** A Ziply topic (`search_topics`, `get_topic_brief`), or what the user pasted. Content already in Ziply can't be loaded from here: ask the user to paste the blog or page, or its key points, and its link.
3. **The link.** The page the posts promote: the link the user gives, or the brand's blog. With none, the posts carry no link — say so.
4. **The user's request.** Their own hashtags, call to action, emoji level, and anything to leave out. These come first.
5. **Voice and context.** `get_brand_profile` for the brand's voice (its brand guideline), restrictions and offerings; `get_digital_twin` for a person's voice; `list_personas` for the audience.
6. **Draft.** For each channel, its own variants — written for that channel, differing in angle or opening. Label each `linkedin-v1`, `x-v2` and so on. Stay within each channel's limit: LinkedIn 3,000 characters; X 280 for a standard post (up to 25,000 only if the user asks for a long post); Instagram caption 2,200; YouTube title 100 and description 5,000.
7. **Hand it over,** grouped by channel, saying where the style came from. The user can pick the variants they like. Offer to save them as one post.

## Who decides style

Emojis, hashtags, link placement and length follow, in order: the user's request, then the person's twin when writing in their voice, then the brand's voice guidance, then the channel's norms, then the house defaults below. Say where the style you applied came from.

**House defaults:** no emoji bullets, no engagement-bait closing questions, no stacks of one-line paragraphs, no hype words, no cliché openings, no blocks of hashtags.

## Reddit as one of the channels

If Reddit is among the channels, write its variants following the Reddit skill's rules, and save them in the same grouped post.

## Instagram and YouTube

This release doesn't create images or video. For Instagram, say what image is needed; Instagram captions can't hold a clickable link, so point to the link in bio instead. For YouTube, write from the transcript or notes the user supplies — never describe a video beyond them.

## Always — these never yield to a request or a setting

- No readiness score for social posts.
- No internal figures or quotes from the brand's own buyers in a public post.
- Nothing invented: no statistics, customers, quotes or credentials that aren't real.
- No writing as a named person without their digital twin and the user's confirmation.
- Never use a word in the brand's `prohibitedKeywords`.
- Saving creates a draft. Publishing happens in Ziply.
