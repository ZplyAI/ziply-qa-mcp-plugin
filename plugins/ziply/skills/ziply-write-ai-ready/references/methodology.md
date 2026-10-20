# Ziply's writing method

**Method version: 2026-10-19.** Pass it as `knowledgeVersion` when saving. It follows the prompts Ziply Content Factory writes blogs, pages and eBooks with; when those prompts change, this file changes with them.

AI answer engines don't rank pages; they lift passages and cite sources. A page earns citations when an engine can take a clear, self-contained, attributed answer from it. Everything below serves that, and a reader at the same time.

## Contents

1. Restrictions come first
2. Use the brand context, specifically
3. Answer first
4. Headings buyers would ask
5. Passages that stand alone
6. One quotable definition
7. Structure that matches the content
8. Claims with sources attached
9. Keywords: coverage, not density
10. The entity, named clearly
11. Links
12. Brand voice
13. SEO details
14. What not to do

## 1 · Restrictions come first

- **Prohibited keywords** (`restrictions.prohibitedKeywords`): never use any of them anywhere — title, headings, body, SEO fields. Check plurals, other verb forms and synonyms that carry the same claim. If the topic needs the idea, rephrase.
- **Scope exclusions** (`restrictions.scopeExclusions`): don't mention, reference or imply anything outside the brand's scope: excluded places, services not offered, clients not served, claims not allowed. If the topic reaches beyond scope, narrow it, or tell the user it can't be written within scope.
- These override everything else: SEO, length, completeness, and what the user asked for. Check the finished draft against both before handing it over.

## 2 · Use the brand context, specifically

- **Personas:** use their actual pain points, frustrations, challenges and benefits from `list_personas`. A generic pain point is worthless.
- **Offerings:** present them as solutions to the reader's problem, shown through outcomes, never as a sales pitch or a feature list. Feature 1–3 relevant offerings at most.
- **Use cases:** use their before and after states and success measures as proof points.
- **Differentiators:** two or three natural mentions, where they're relevant.
- **Pillar and clusters:** the pillar's keywords and the cluster's angle set what the piece covers.

## 3 · Answer first

Open with the answer to the reader's question, in plain words, in the first paragraph. Context, history and caveats come after it. A list or table is never the very first thing; put one sentence of answer before it.

## 4 · Headings buyers would ask

Where it reads naturally, phrase H2s and H3s the way a buyer asks: a real question ("How does graph retrieval reduce hallucinations?") or a "how to" phrase. A statement that merely starts with "Why" isn't a question. Don't force every heading into one.

## 5 · Passages that stand alone

Each paragraph that carries a key point names its subject instead of opening with "It", "This", "These" or "That" pointing back. "Graph retrieval reduces hallucinations because…" survives being lifted; "This reduces hallucinations because…" doesn't.

## 6 · One quotable definition

Include one crisp, one-sentence definition of the central concept, early: "X is a Y that Z".

## 7 · Structure that matches the content

- Steps, options and criteria go in lists; comparisons with several attributes go in tables.
- One H1 (the title). Blogs and pages don't skip heading levels; eBooks follow their own heading rule (ebook.md).
- Close longer pieces with a summary or an FAQ that answers the main question and its common variants directly.
- Vary sentence and paragraph length. No walls of text, no stacks of one-line paragraphs.
- Images and video aren't uploaded from here. Where a visual would help (a process diagram, a comparison, a data chart), say so in the hand-over, with its alt text; don't put image markup in the body. A chart's key numbers also belong in the text.

## 8 · Claims with sources attached

- A statistic or factual claim needs its source in the same sentence (a link), or a source line directly after it. A link two paragraphs later doesn't count.
- Sources are the topic brief's sources, the links the user gave, pages the user asked you to use, and sources you find on the web yourself. A web source counts only once you've opened it and it says what you cite: prefer the primary source (the study, the report, the official documentation) over a page quoting it, and never cite a figure the source doesn't state. Attribute naturally ("according to Gartner's 2025 survey…") and link.
- The brand's own prices, plan limits and offers are its terms, not claims. A comparative result ("customers save 40% versus X") is a claim and needs a source.
- First-party data (the brand's research or usage figures) is a strong citation magnet: present it as the brand's own, with one line on how it was gathered. Only when the user or Ziply provides it.

## 9 · Keywords: coverage, not density

- The pillar's primary keyword goes in the title, the first 100 words, at least two H2s and the conclusion, where it reads naturally.
- Secondary keywords and the cluster's long-tail phrases appear naturally across sections. Roughly 1–2% is the ceiling, not a target; if a keyword feels forced, use it less.
- Cover the related concepts a complete answer includes. Repetition beyond natural use hurts.

## 10 · The entity, named clearly

Name what the page is about (the product, concept or company) in full in the title and the opening paragraph. Use the same term for it throughout.

## 11 · Links

- Link to the brand's own related pages with descriptive anchor text that says where the link goes. `suggest_internal_links` returns the pages of the brand's site (its Site Audit crawl, indexed every night) closest in meaning to each section, pages in the same content cluster or pillar first. Link only the ones a reader of that section would actually want, each from a phrase in a sentence of the section it fits. Link only URLs from that list.
- `search_content` finds what the brand has saved in Ziply, but its `openUrl` opens Content Factory, not the published page: never use it as a link. Link a saved piece only through its published URL from `suggest_internal_links`, or one the user confirms; otherwise suggest the link in the hand-over.
- Never "click here", "read more" or a bare URL as anchor text, and never more links than the passage needs.

## 12 · Brand voice

Apply the brand guideline from `get_brand_profile` (`brandGuideline`): its personality, tone and phrasing. When writing as a person, their digital twin's voice guide and samples come first, after the user confirms the person.

## 13 · SEO details

For blogs and pages, prepare: meta title (up to 60 characters, with the primary keyword), meta description (up to 155 characters, with the primary keyword and a reason to click), a 1–2 sentence summary, a slug (lower-case words joined by hyphens) and 5–10 keywords. They must describe the actual draft, not what it could have been.

## 14 · What not to do

- Invent statistics, sources, customers, quotes, credentials or authors.
- Fill an optional template section with nothing behind it: leave it out.
- Pad for length or repeat keywords.
- Hide the answer behind a long introduction.
- Name or disparage competitors beyond what the template's competitor setting and the sources support.
