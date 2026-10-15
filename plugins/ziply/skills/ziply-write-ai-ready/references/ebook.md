# eBooks

**Purpose:** go deep on a subject that justifies length, in chapters that each stand on their own, because engines and readers often take one chapter without the rest.

## Headings: required

Ziply finds an eBook's chapters by their headings: chapter search, reading a few chapters (`get_content`) and replacing chapters (`update_draft`) all depend on it. Write every eBook in this shape, the same one Content Factory uses:

```markdown
# The eBook title

*The subtitle*

### Executive Summary
…
### How to Use This Guide
…
### Table of Contents
- Chapter 1: Why evaluation goes wrong
- Chapter 2: …

### Chapter 1: Why evaluation goes wrong
The chapter's answer-first opening…

#### A section of the chapter
…
#### Key Takeaways
…

### Chapter 2: …

### Conclusion
### Glossary
### Resources
```

- **The title** is the only H1.
- **Front matter, chapters and back matter** are H3. A chapter heading is exactly `Chapter <number>: <title>`, numbered from 1 with no gaps.
- **Inside a chapter, use H4 or lower** for sections, callouts and takeaways. An H2 or H3 inside a chapter ends the chapter there.
- **Only chapters start with "Chapter".** List the table of contents as plain list items, never headings, and don't begin front or back matter headings with "Chapter".

## Every chapter

- An opening of 100–200 words that answers the chapter's question first (or opens with the template's pattern: a question, a statistic, a scenario).
- The template's number of sections, each an H4.
- Examples, frameworks or checklists where they help; callouts (Pro tip, Common mistake, Key insight) as H4s.
- A close: a short summary, action items or a preview of the next chapter, per the template.
- Its own sources, cited in the chapter. Don't rely on a bibliography at the end.

## Front and back matter

Unless the template says otherwise:

- **Front:** Executive Summary (200–400 words), How to Use This Guide (100–150 words), Table of Contents, Key Definitions.
- **Back:** Conclusion, Call to Action, Glossary, Resources.
- **Data-driven templates** (whitepaper, reports, research, benchmark) add **Methodology** at the front and **References** at the back, and **need real data from the user or Ziply**. Never invent findings.

## Promotion, competitors and pricing

Each template sets how much of the eBook is about the brand, how it treats competitors and pricing:

- **Promotion:** 0–5% (pure education, the brand only in the About and Call to Action), 5–15% (subtle: the brand as one example among others), 15–25% (moderate), 25–40% (strong), 40–60% (product-focused).
- **Competitors:** Never mention · Category only (e.g. "other platforms") · Name objectively · Name with differentiation. Every factual claim about a named competitor needs a source.
- **Pricing:** Never discuss · General ranges only · Specific, and only figures the user gives.

## Templates

These are Ziply's standard eBook templates, the same ones Content Factory offers. Pick the one that fits and say which you used; pass its key as `templateId` when saving. The words-per-chapter range times the chapter count sets the length; agree a shorter version with the user when that suits them better.

A customer may have their own eBook templates (presets) in Ziply; this assistant can't read them. If the user mentions one, ask them to paste its settings.

| Template (`templateId`) | Main goal | Chapters × words | Promotion | Competitors | Pricing | Chapter pattern |
|---|---|---|---|---|---|---|
| Buyer Guide (`ebook-buyer-guide`) | Lead generation | 6–8 × 1,200–1,800 | 5–15% | Name objectively | General ranges | Opens with a question; closes with summary + action; awareness to decision |
| Whitepaper (`ebook-whitepaper`) | Thought leadership | 9–12 × 1,800–2,500 | 0–5% | Category only | Never | Problem → solution arc; same formula each chapter; closes with summary + preview |
| How-To Guide (`ebook-how-to`) | Customer education | 6–8 × 800–1,200 | 5–15% | Category only | Never | Sequential steps; summary + action |
| Ultimate Guide (`ebook-ultimate-guide`) | Thought leadership | 13–15 × 1,800–2,500 | 5–15% | Name objectively | General ranges | Foundations first, then depth; varied openings |
| Industry Report (`ebook-industry-report`) | Thought leadership | 9–12 × 1,200–1,800 | 0–5% | Category only | General ranges | Chronological; opens with a statistic; data-driven |
| State of the Industry (`ebook-state-of-industry`) | Thought leadership | 6–8 × 1,200–1,800 | 0–5% | Name objectively | General ranges | Most important first; opens with a statistic; data-driven |
| Trend Report (`ebook-trend-report`) | Thought leadership | 6–8 × 1,200–1,800 | 0–5% | Category only | General ranges | Chronological; opens with a question; data-driven |
| Research Study (`ebook-research-study`) | Thought leadership | 9–12 × 1,800–2,500 | 0–5% | Never mention | Never | Problem → solution arc; same formula each chapter; data-driven |
| Benchmark Report (`ebook-benchmark`) | Thought leadership | 6–8 × 1,200–1,800 | 0–5% | Category only | Never | Compare and contrast; opens with a statistic; data-driven |
| Case Study Compilation (`ebook-case-studies`) | Sales enablement | 6–8 × 1,200–1,800 | 25–40% | Name with differentiation | General ranges | One customer story per chapter; **only real stories the user provides** |
| Best Practices Guide (`ebook-best-practices`) | Customer education | 6–8 × 1,200–1,800 | 5–15% | Category only | Never | Strategic to tactical; summary + action |
| Playbook (`ebook-playbook`) | Sales enablement | 6–8 × 1,200–1,800 | 15–25% | Category only | Never | Independent plays; each closes with action items |
| Strategic Framework (`ebook-framework`) | Thought leadership | 6–8 × 1,200–1,800 | 5–15% | Category only | Never | Foundations first; opens with a question |
| ROI Calculator Guide (`ebook-roi-guide`) | Sales enablement | 3–5 × 500–800 | 25–40% | Name with differentiation | Specific (user's figures only) | Sequential; worked examples; action items |
| Comparison Guide (`ebook-comparison`) | Lead generation | 6–8 × 1,200–1,800 | 15–25% | Name with differentiation | Competitor comparisons (sourced) | Compare and contrast; opens with a question |
| Implementation Guide (`ebook-implementation`) | Customer retention | 6–8 × 1,200–1,800 | 40–60% | Never mention | Never | Sequential; action items |
| Quick Start Guide (`ebook-quick-start`) | Customer education | 3–5 × 500–800 | 40–60% | Never mention | Never | Sequential; action items; 1,000–2,000 words in all |
| Template Toolkit (`ebook-template-toolkit`) | Customer education | 3–5 × 500–800 | 15–25% | Never mention | Never | Independent templates; action items |
| Maturity Model Guide (`ebook-maturity-model`) | Customer education | 3–5 × 1,200–1,800 | 5–15% | Category only | Never | One stage per chapter; summary + action |
| Checklist Guide (`ebook-checklist`) | Customer education | 3–5 × 500–800 | 5–15% | Never mention | Never | Sequential checklists; action items |
| Myth-Busting Guide (`ebook-myth-busting`) | Thought leadership | 6–8 × 1,200–1,800 | 5–15% | Category only | General ranges | Myth, then evidence, then the truth; opens with a question |
| Problem-Solution Brief (`ebook-problem-solution`) | Sales enablement | 3–5 × 500–800 | 25–40% | Name with differentiation | General ranges | Problem → solution arc; opens with a scenario |
| Manifesto (`ebook-manifesto`) | Thought leadership | 3–5 × 500–800 | 15–25% | Category only | Never | Thesis, challenge, synthesis; a preface instead of an executive summary |
| Handbook (`ebook-handbook`) | Customer education | 13–15 × 1,800–2,500 | 5–15% | Category only | Never | Independent reference chapters; summary only |
| Roadmap Guide (`ebook-roadmap`) | Customer education | 6–8 × 1,200–1,800 | 15–25% | Category only | General ranges | One phase per chapter, in order |
| Survival Guide (`ebook-survival-guide`) | Customer education | 6–8 × 1,200–1,800 | 5–15% | Category only | Never | Problem → solution per chapter; opens with a scenario; action items |

## Long eBooks

A long eBook may not fit in one reply. Agree the outline first (the table of contents), then write it a few chapters at a time and assemble the whole text before saving. Never save a partial eBook as if it were complete.
