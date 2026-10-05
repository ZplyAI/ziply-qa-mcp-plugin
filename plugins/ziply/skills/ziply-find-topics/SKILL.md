---
name: ziply-find-topics
description: Recommends what to write next for the user's brand from Ziply's ranked topic queue, drawn from the brand's sales conversations, media and market intelligence, AI-visibility gaps and the team's own plans. Use whenever the user asks what to write about, wants content ideas, content gaps or a content plan for their company, or asks which topics matter most right now, even if they don't mention Ziply.
---

# Find topics to write about

Ziply ranks topics by evidence: what buyers ask in sales conversations, what the market and media are discussing, where the brand is missing from AI answers, and what the team has planned. Surface the strongest topics honestly and help the user pick one. Don't invent a list.

## Steps

1. **Search the queue.** Call `search_topics` with anything the user specified: words from the subject (`query`), a pillar (use `list_pillars` to match a name to its `pillarId`), or a source (`Sales Intelligence`, `Media Intelligence`, `AI Visibility Gap`, `Manual` for the team's own plans). Default to the top 10 by score.
2. **Present the topics.** For each, give the title, where it came from, and one line on why it ranks where it does — its score, importance and urgency, or the strongest part of its score breakdown from `get_topic_brief` when the user wants detail. Say when content has already been written from a topic (`isPostCreated`). Keep the list easy to scan.
3. **Be honest about ranking.** A topic with a `null` score hasn't been scored by Ziply yet. List those separately, saying they're unscored, rather than mixing them into the ranking.
4. **Offer the next step.** Ask which topic the user wants, and offer a brief, to go straight to writing, or to start with social posts or a Reddit discussion.

## When the user wants ideas beyond the queue

Brainstorming is fine, but label it. Keep two separate groups: **In Ziply's topic queue** and **Suggestions not in Ziply**. Never present a brainstormed idea as one of Ziply's evidenced topics. If the user likes a suggestion, they can add it in Ziply as a planned topic; this release can't create topics from here.

## Don't

- Invent scores, evidence or sources.
- Hide unscored topics or present them as ranked.
- Recommend topics for a brand other than the user's without saying so.
