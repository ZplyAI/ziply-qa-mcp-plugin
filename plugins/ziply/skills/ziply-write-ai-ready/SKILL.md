---
name: ziply-write-ai-ready
description: Writes long-form content for the user's company website, such as blog posts, web pages, eBooks and comparison pages, using the brand context and topic brief Ziply holds. Use whenever the user asks to write, draft, create or outline a blog post, article, page, eBook or comparison for their company or brand, even if they don't mention Ziply. Not for social posts or Reddit, which have their own skills, and not for personal writing, emails or code.
---

# Write long-form content

Blog posts, pages and eBooks for the brand's own site, written from what Ziply holds about the brand: its voice, its restrictions, its personas, its pillars and the topic's evidence.

## When the request just says "post"

If the user asks for a "post" with no channel named and nothing indicating length, ask one question first: *a blog post for your site, or a social post — and if social, which channels?* For a social post, hand over to the social skill.

## Steps

1. **Resolve the essentials.** Which type: blog post, page (a landing page, a pillar page for one pillar, or a cluster page for one cluster of a pillar) or eBook. A comparison is a blog post or page structured as a comparison, and needs a competitor and the criteria to compare on.
2. **Load the brief and context.** The topic brief (`get_topic_brief`) where there's a topic; the brand voice, restrictions and offerings (`get_brand_profile`) or a person's voice (`get_digital_twin`); the persona (`list_personas`); the pillar and its clusters (`list_pillars`); and competitors (`list_competitors`) for a comparison.
3. **Draft** for AI answer engines and readers alike: answer the main question first, one idea per section with clear headings, claims tied to the brief's sources with links in the same sentence, the persona's own terms, and the brand's voice from its brand guideline.
4. **Respect the brand's restrictions.** Never use a word in `prohibitedKeywords`, and stay out of anything in `scopeExclusions`.
5. **Hand it over.** Say which sources and Ziply context it was written from. Ziply's AI-readiness check isn't available in this release, so give no score. Offer to save it to Ziply.

## Always

- Never estimate or invent an AI-readiness score.
- Nothing is invented: no statistics, customers, quotes, credentials or sources that Ziply or the user didn't provide.
- No writing as a named person without their digital twin and the user's confirmation.
- Saving creates a draft. Publishing happens in Ziply.
