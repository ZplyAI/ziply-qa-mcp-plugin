# Blog posts

**Purpose:** answer one buyer question well enough to be the source an engine cites.

**Default length:** 1,200–1,800 words, unless the user or the template says otherwise. Substance over padding.

**Every blog post has:** a title naming the entity and the subject; an answer-first opening; sections headed, where natural, by the questions buyers ask; the quotable definition early; sourced evidence; and a closing summary or FAQ.

## Templates

These are Ziply's standard blog templates, the same ones Content Factory offers. Pick the one that fits the request and say which one you used; if none fits, use the general shape above. Pass the template key as `templateId` when saving.

A customer may have their own templates (presets) in Ziply; this assistant can't read them. If the user mentions one, ask them to paste its sections.

Section lists are in order. Skip optional sections when nothing real supports them.

| Template (`templateId`) | Use it to | Sections |
|---|---|---|
| How-To / Tutorial (`blog-how-to`) | Teach a task step by step | Title ("How to [outcome] in [context]") · Introduction 150–250 words: problem, why now, what the reader will achieve, what they need, time needed · Prerequisites · Overview of the steps · Steps (5–12; each: objective, instructions 100–200 words, tips, how to check it worked) · Troubleshooting · Next steps · Results · FAQ (5–8, 50–100 words each) · Related resources · Call to action · Author bio |
| Thought Leadership / Opinion (`blog-thought-leadership`) | Argue a clear point of view | Title (a clear stance) · Opening hook 100–150 words · Thesis (1–2 sentences) · Context 200–300 words · Three supporting arguments (200–250 words each, with evidence) · Counterarguments and responses · Implications 200–300 words · Why the author can speak to it · Call to reflection or action · Conclusion 150–200 words · Discussion prompt |
| Industry Trends & Analysis (`blog-industry-trends`) | Analyse current trends | Title ("[N] trends shaping [industry] in [year]") · Executive summary 150–200 words · Introduction and context · Trends 1–3 (each: what's happening, evidence, drivers, implications, optional who's leading and timeline) · Trends 4–5 (optional, shorter) · How the trends connect · Winners and losers · Expert perspectives · What this means for you · Looking ahead · Conclusion and takeaways · Related research |
| Case Study / Customer Story (`blog-case-study`) | Show a real customer's results | Title · Quick stats · Company background 150–200 words · Challenge 300–400 · Evaluation 200–300 · Solution 400–500 · Implementation 200–300 · Results 400–600 · Unexpected benefits · Lessons learned · What's next · Key takeaways · About the company · Call to action. **Only with a real customer story the user provides**, cleared for publication. |
| Product Announcement / Feature Highlight (`blog-product-announcement`) | Announce a product or feature | Title · Announcement 100–150 words · Problem or opportunity 200–300 · What it is 300–400 · Key features · How it works 400–500 · Use cases and examples 300–400 · Customer or beta quotes (only real ones) · Technical details (optional) · Pricing and availability · Getting started · What's next · FAQ · Call to action |
| Listicle / List (`blog-listicle`) | A scannable list of tips, tools or resources | Title · Introduction 150–250 words · Contents (optional) · List items · Bonus items (optional) · Comparison (optional) · How to choose · Implementation tips · Conclusion · Reader engagement · Related resources · Call to action |
| Comparison / vs (`blog-comparison`) | Help the reader choose between options | Title · Quick comparison table · Introduction 200–300 words · Overview of option A and of option B (200–300 each) · Head-to-head comparison · Detailed feature comparison · Pricing · Use-case scenarios · Pros and cons · Migration considerations · Reviews (only real, sourced ones) · Decision framework · Bottom-line recommendation · FAQ · Next steps · Call to action. Needs the competitor (`list_competitors`) and the criteria. Every factual claim about a competitor needs a source. |
| Problem-Solution (`blog-problem-solution`) | Address one problem and its solution | Title · Hook 100–150 words · The problem 300–400 · Why usual solutions fail 200–300 · Solution overview 200–300 · Solution in detail · Implementation 300–400 · Real-world example 200–300 · Expected results 200–300 · Common mistakes · Advanced tips · Alternatives (optional) · Conclusion · Call to action |
| Data / Research-Driven (`blog-research`) | Share original research | Title · Key findings · Introduction 200–300 words · Methodology 200–300 · Findings 1–3 · More findings (optional) · Breakdowns · Surprising insights · Expert analysis 300–400 · Implications and recommendations · Looking forward · Conclusion · Methodology appendix · Full-report call to action. **Only with data the user or Ziply provides**; never invent findings. |
| Interview / Expert Roundup (`blog-expert-roundup`) | Share experts' views | Interview: title · introduction 150–200 words · expert bio · questions and answers · key takeaways · about the expert's company. Roundup: title · introduction · the panel · the question · responses · common themes · differing views · analysis · what to do · conclusion. **Only with real answers the user provides.** |
| Best Practices / Framework (`blog-framework`) | Teach a methodology | Title · Introduction 200–300 words · Framework overview · When to use it · Components or stages · Framework in practice 400–600 · Example 300–400 · Adapting it · Pitfalls and fixes · Measuring success · Advanced uses · Tools and resources · Getting started · FAQ · Conclusion · Call to action |
| News / Industry Update Commentary (`blog-news-commentary`) | Analyse a piece of news | Title · News summary 150–200 words · Why it matters 150–200 · Background 200–300 · Analysis 400–600 · Winners and losers · What happens next · What it means for you · Alternative view · Historical parallels · Expert quotes (optional, real only) · Related developments · Bottom line · Call to action |
| ROI / Value Calculator (`blog-roi`) | Help the reader estimate value | Title · Introduction 150–200 words · The opportunity 200–300 · How the calculation works · The calculation (as a worked example or table; the page can't hold an interactive calculator) · Understanding the results 300–400 · ROI breakdown · Examples · What affects ROI · Maximising it · Timeline · Beyond the numbers · Next steps · FAQ · Call to action |
| Checklist / Template (`blog-checklist`) | Give an actionable checklist | Title · Introduction 150–200 words · How to use it · Before you begin · Categories · The checklist · Critical vs optional items · Common pitfalls · Quality checks · Real-world use · Adapting it · Tools · Measuring completion · What's next · Resources · Call to action |

## SEO

Every blog post is saved with `seo`: meta title, meta description, summary, slug and keywords (methodology.md, section 13).
