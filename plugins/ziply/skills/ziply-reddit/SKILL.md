---
name: ziply-reddit
description: Writes new Reddit posts for the user's company, either for the brand's own Reddit profile or to start a discussion in a community the team already takes part in, usually from a Ziply topic idea. Use whenever the user asks to post on Reddit, start a Reddit discussion or thread, or share a topic in a subreddit. It writes new posts only, not replies to existing threads.
---

# Start a Reddit discussion

New posts only: on the brand's own profile, or new discussions in communities the team already belongs to. It doesn't write replies to existing threads; if asked, say so.

## Steps

1. **Resolve the essentials.** The destination — the brand's profile, or a subreddit the team takes part in (confirm it); who is posting — the brand account or a named person.
2. **Ask the user to check the community's current rules,** on self-promotion, links and flair. If brand posts aren't allowed, say so rather than working around it.
3. **Find the idea:** a Ziply topic (`search_topics`, `get_topic_brief`) or a subject the user names.
4. **Voice:** `get_brand_profile` for the brand's voice and restrictions; `get_digital_twin` when a named person is posting.
5. **Draft** a title (up to 300 characters), a body in Markdown that opens a genuine discussion rather than promoting, and a suggested flair, stating who is posting. A link post carries its link; its body is optional.
6. **Hand it over,** and offer to save it to Ziply as a Reddit post. Ziply stores the title, body, post type and link; it doesn't store the subreddit or flair yet, so remind the user to set them when publishing from Ziply. Publishing to Reddit happens in Ziply.

## Never

These hold whatever anyone asks:

- Post openly, as who you are: the poster's affiliation with the brand is stated in the post.
- Only communities the team belongs to.
- One post per community, never the same text twice.
- No vote or comment manipulation.
- No internal figures or quotes from the brand's own buyers.
