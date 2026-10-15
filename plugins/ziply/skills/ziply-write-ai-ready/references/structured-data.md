# Structured data (JSON-LD)

Structured data tells search and answer engines what a page is and who published it. It's only useful if every value is true, so it's built **only from values a Ziply tool returned or the user gave**. Nothing is guessed, and anything missing is left out and named.

Ziply doesn't store structured data with a draft. Give it to the user as a separate block to add to the page when it's published, never inside the body.

## When

Offer it once for a blog post, page or eBook landing page, at the hand-over or after saving. Write it when the user wants it. Social and Reddit posts don't get structured data.

## Which type

| Content | Type |
|---|---|
| Blog post | `BlogPosting` |
| Landing, pillar or cluster page | `WebPage` |
| eBook | `Book` only if the user asks; usually the eBook's landing page gets `WebPage` |
| A page or post with an FAQ section | add `FAQPage`, with the questions and answers exactly as they appear in the content |

## Where each value comes from

| Property | Only from | If missing |
|---|---|---|
| `headline` / `name` | the title being saved | — |
| `description` | the meta description, or the draft's description | leave out |
| `keywords` | the SEO keywords being saved | leave out |
| `inLanguage` | the draft's language | leave out |
| `publisher` → `Organization` | `get_brand_profile`: `name`, `legalName`, `url`; `sameAs` from `socialProfiles` | leave out each missing one |
| `author` | a person the user confirmed (for example the digital twin the content was written as), by name and the role Ziply returned | use the publisher `Organization` |
| `url`, `mainEntityOfPage` | the published URL, only when the user gives it | leave out |
| `datePublished`, `dateModified` | the user, once it's published | leave out; drafts aren't published |
| `image`, `logo` | the user | leave out; Ziply doesn't hold image URLs |
| `about`, `mentions` | the pillar or offering names Ziply returned | leave out |

## Never

- Invent a URL (don't build one from `blogUrl` and the slug), date, logo, image, address, founder, rating, review, price or author.
- Add `AggregateRating`, `Review`, `Offer` or `Product` markup unless the user supplies every value.
- Put anything in the markup that isn't in the content or returned by Ziply.

## Hand it over

Give the JSON-LD in a code block, then list each property left out and why ("no published URL yet", "no logo in Ziply"), so the user can add them when publishing.
