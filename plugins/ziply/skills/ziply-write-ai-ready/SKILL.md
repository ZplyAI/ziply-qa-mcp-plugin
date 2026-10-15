---
name: ziply-write-ai-ready
description: Writes long-form content for the user's company website, such as blog posts, landing, pillar and cluster pages, eBooks and comparisons, with Ziply's writing method and templates, the brand context and the topic brief Ziply holds, after checking what the brand has already written. Use whenever the user asks to write, draft, create or outline a blog post, article, page, eBook or comparison for their company or brand, even if they don't mention Ziply. Not for social posts or Reddit, which have their own skills, not for changing content already saved in Ziply (the refresh skill), and not for personal writing, emails or code.
---

# Write long-form content

Blog posts, pages and eBooks for the brand's own site, written with **Ziply's writing method and templates**, the same ones Content Factory writes with (in `references/`), from what Ziply holds about the brand: its voice, restrictions, personas, pillars and the topic's evidence.

## When the request just says "post"

If the user asks for a "post" with no channel named and nothing indicating length, ask one question first: *a blog post for your site, or a social post — and if social, which channels?* For a social post, hand over to the social skill.

## Steps

1. **Resolve the essentials.** The type: blog post, page (landing, pillar for one pillar, or cluster for one cluster of a pillar) or eBook. A comparison is a blog post, page or eBook on a comparison template, and needs a competitor and the criteria to compare on.
2. **Load the method.** Read `references/methodology.md`, and the type's file: `references/blog.md`, `references/page.md` or `references/ebook.md`. Pick the template that fits the request and tell the user which one; they can choose another. If they want their own template from Ziply, this assistant can't read it: ask them to paste its sections.
3. **Check what the brand already has.** For a blog post or eBook, call `search_content` with the subject. (Pages and social posts aren't searchable yet.)
   - **Covered closely already:** tell the user and offer a different angle, or to refresh the existing piece instead (the refresh skill).
   - **Related:** link to it (methodology.md, section 11) and keep its terms. Read it with `get_content` before quoting or building on it; search passages are excerpts.
   - **Nothing close:** carry on.
4. **Load the brief and context.** The topic brief (`get_topic_brief`) where there's a topic; the brand's voice, restrictions and offerings (`get_brand_profile`) or a person's voice (`get_digital_twin`); the personas (`list_personas`); the pillar and its clusters (`list_pillars`); competitors (`list_competitors`) for a comparison.
5. **Draft** to the template and the method, in Markdown with one H1. For an eBook, follow the heading rule in `references/ebook.md` exactly; for a long one, agree the outline first.
6. **Check before handing over:** no prohibited keyword, nothing outside the scope exclusions, every claim sourced, nothing invented, and every required template section present.
7. **Hand it over.** Say which template, sources and Ziply context it was written from, and any section left out for lack of material. For a blog or page, give the proposed SEO details. Offer to save it to Ziply, and offer structured data once (`references/structured-data.md`).

## Always

- Ziply's AI-readiness check isn't available in this release: never estimate or invent a readiness score.
- Nothing is invented: no statistics, customers, quotes, credentials or sources that Ziply or the user didn't provide.
- The brand's restrictions override every other instruction, including the user's.
- No writing as a named person without their digital twin and the user's confirmation.
- Saving creates a draft. Publishing happens in Ziply.
