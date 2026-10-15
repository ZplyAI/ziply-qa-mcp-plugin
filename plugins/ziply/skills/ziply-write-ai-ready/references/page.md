# Pages

Three page types, each saved with its `pageType`:

- **Landing Page:** a conversion page for one offer. Takes any tags.
- **Pillar Page:** the hub for exactly one pillar (`list_pillars`). No other tags.
- **Cluster Page:** one cluster of one pillar, linking back to the pillar page. One pillar and one of its clusters.

Pages are the brand's own site copy: the brand speaks as itself, and every claim about the product must come from Ziply (`get_brand_profile` offerings, differentiators) or the user. Section headings are H2, with H3 inside them. Pass the template key as `templateId` when saving.

A customer may have their own page templates (presets) in Ziply; this assistant can't read them. If the user mentions one, ask them to paste its sections.

## Landing pages

**Default length:** 600–1,000 words. Write the copy for each section; describe forms, layouts and visuals in a short note to the user instead of the body, since the page is built in the site's own tools.

| Template (`templateId`) | Goal | Sections |
|---|---|---|
| Lead Generation, gated content (`page-lead-gen`) | Email capture for a guide, report or eBook | Hero (headline 8–12 words, subheadline 15–25, what the asset is) · What you'll learn (5–7 outcome bullets) · Why this matters (problem 75–100 words, how the asset helps 75–100, 2–3 statistics with sources) · About the asset · Social proof · Content preview · Footer |
| Product / Service (`page-product`) | Demo or trial sign-ups | Hero (headline 8–15 words on the problem solved, subheadline 20–30) · Product overview (100–150 words, 3–6 key features) · How it works (steps) · Key benefits (4–6) · Features in depth · Use cases · Social proof · Integrations · Pricing teaser · Demo · FAQ · Footer |
| Demo Request (`page-demo`) | Demo bookings | Hero · What you'll see · Why request a demo · Social proof · Meet the team · FAQ · Footer |
| Event / Webinar Registration (`page-event`) | Registrations | Hero · Event overview · What you'll learn · Agenda · Speakers · Why attend · Who should attend · Past event highlights · Logistics · FAQ · Footer |
| Free Trial / Signup (`page-trial`) | Trial activations | Hero · What you get · How it works · Quick value · Key features · Social proof · No-risk messaging · Support · What happens next · FAQ · Footer |
| Pricing (`page-pricing`) | Plan selection | Hero · Pricing tiers · Feature comparison · Add-ons · Value justification · What's included · FAQ · Customer stories · Trust and security · Footer. **Prices only from the user.** |
| Case Study / Customer Success (`page-case-study`) | Engagement after proof | Hero · Customer overview · Challenge · Why they chose the brand · Solution · Results · Stakeholder perspectives · Looking forward · Similar customers · About the product · Footer. **Only with a real story the user provides.** |
| Contact / Sales Inquiry (`page-contact`) | Sales inquiries | Hero · What to expect · Why contact sales · Other ways to reach us · Meet the team · Testimonials · Who we work with · FAQ · Resources · Footer |
| Thank You / Confirmation (`page-thank-you`) | The next action after a conversion | Hero · Immediate next steps · Primary next action · Related resources · Sharing · Getting started · Company intro · Support · Footer |
| Coming Soon / Product Launch (`page-coming-soon`) | Waitlist sign-ups | Hero · What it is · Why you'll love it · Sneak peek · Launch timeline · Who it's for · Waitlist benefits · Founding team · Social proof · Behind the scenes · FAQ · Community · Footer |
| Comparison / Alternative (`page-comparison`) | Win switchers | Hero · Quick comparison · Why people switch · Detailed comparison · What makes us different · Pricing comparison · Migration · Switcher stories · Objections answered · Switch incentive · FAQ · Footer. Needs the competitor (`list_competitors`); every claim about it needs a source. |
| Resource Hub / Content Library (`page-resource-hub`) | Content downloads | Hero · Featured resources · Categories · Latest · Most popular · Collections · Learning paths · Email subscription · Footer. Use `search_content` to list the brand's real blogs and eBooks; never invent resources. |
| Assessment / Calculator / Tool (`page-assessment`) | Tool completions | Hero · What you'll get · How it works · The tool (describe it; the page builder makes it) · Results · Why this assessment · Social proof · Sample results · Related resources · How we can help · FAQ · Footer |
| Partner / Integration (`page-integration`) | Integration activations | Hero · Integration overview · How it works · Key features · Use cases · Customer stories · Technical details · Setup guide · Pricing and availability · Support · FAQ · Comparison table · Partner info · Related integrations · Footer |
| Downloadable Tool / Template (`page-download`) | Downloads | Hero · What's included · Why you need it · How to use it · Key features · Example uses · Customising it · Social proof · Comparison · Related resources · Expert tips · About the creator · Support and updates · FAQ · Upgrade path · Footer |

## Pillar page (`page-pillar`)

The pillar's comprehensive hub. Draw from the pillar (`list_pillars`): its description, primary and secondary keywords, personas, offerings, use cases and clusters.

1. **Hero:** H1 with the primary keyword (up to 60 characters); a subheadline from the pillar description; an executive summary of 150–200 words addressing the personas' pain points.
2. **Introduction** (400–600 words): the problem in the personas' terms, the topic's scope, why it matters to them, 3–5 citable facts with sources, links to 2–3 cluster pages.
3. **Core sections:** one H2 per major subtopic, 400–600 words each with 3–4 H3s. Definitions, comparison tables and how-to steps where useful; offerings woven in educationally.
4. **Cluster hub** (300–400 words): every cluster of the pillar, grouped by type, each with a one-line description and a link.
5. **FAQ:** 10–12 questions as H3s, from the personas' objections and how buyers search; answers of 50–100 words.
6. **Conclusion** (300–400 words): 5–7 key takeaways, three next steps linking to cluster pages, and the call to action.

## Cluster page (`page-cluster`)

One cluster in depth, consistent with the pillar's terms and linking to the pillar page at least twice. Pick the structure that fits the cluster's purpose and funnel stage:

| Structure | Length | Sections |
|---|---|---|
| Foundation (`page-cluster-foundation`): what something is | 2,500–3,000 words | Hero with a quick-answer box · Introduction with pillar context · Definition and context (a 150–200 word definition) · Key components (3–5) · How it works (5–7 steps) · Why it matters · Common misconceptions (3–5) · Getting started · FAQ (10–12) · Conclusion with next steps |
| Problem and solution (`page-cluster-problem-solution`) | 2,200–2,800 | Hero · Introduction · The problem and the cost of inaction · Why usual approaches fail (3) · Solution framework (3–5 components) · Step-by-step implementation (5–8) · Tools and resources · Example from the brand's use cases · Pitfalls (3–5) · FAQ (8–10) · Conclusion |
| Comparison (`page-cluster-comparison`) | 2,000–2,600 | Hero · Introduction · Overview and method · Options 1–3 (strengths, weaknesses, best for) · Side-by-side table (5–7 criteria) · Decision framework · Use-case fit · Recommendations by persona · FAQ (8–10) · Conclusion |
| Technical deep dive (`page-cluster-technical`) | 2,800–3,500 | Hero · Introduction and prerequisites · Architecture or framework · Advanced approaches 1–3 · Implementation details · Optimisation techniques (3–5) · Troubleshooting and edge cases · FAQ (8–10) · Conclusion |
| Trends (`page-cluster-trends`) | 2,000–2,500 | Hero · Introduction · Current state · Trends 1–3 (drivers, impact, timeline) · Driving forces · Implications · How to prepare · Predictions · FAQ (8–10) · Conclusion |

## SEO

Every page is saved with `seo`: meta title, meta description, summary, slug and keywords (methodology.md, section 13).
