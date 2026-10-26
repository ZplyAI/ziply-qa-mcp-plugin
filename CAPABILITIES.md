# What the Ziply plugin can do

The Ziply plugin connects Claude and ChatGPT to your Ziply workspace. The assistant reads your
brand context, topic queue, saved blogs and eBooks, and the files in your library from Ziply, writes content in your brand's
voice with Ziply's writing method and templates, checks it against Ziply's AI-readiness rules,
suggests links to your own pages, and saves it to Ziply Content Factory as a draft for your team
to review. It can also update draft blogs and eBooks. It never publishes anything.

## Before you start

- **Ziply plan:** Growth or Scale, with an active subscription. On other plans the plugin
  connects but tells you the connector isn't included. The AI-readiness check, link
  suggestions and the library tools (your uploaded files) also need Content Factory on the plan
  (included from Growth).
- **Your Ziply account:** the first time you use the plugin, sign in with your Ziply account and
  allow access. The assistant then sees only your own company's data.
- **Where it works:**
  - **Claude:** chat (web, desktop, mobile), Cowork and Claude Code.
  - **ChatGPT:** Work and Codex in the ChatGPT desktop app.

## What you can ask for

| Ask | What you get |
|---|---|
| "Is Ziply connected?" | Your company, plan, brand and connected blog sites, and what you can do |
| "What should we write next?" | Topics from your Ziply queue, highest opportunity score first, with where each came from: sales conversations, media and market intelligence, AI-visibility gaps or your team's plans |
| "Brief me on this topic." | Why the topic matters, its audience, pillar and clusters, key insights and data points, source links, competitive angles, keywords and journey stage, and what you've already written on it |
| "What have we written about pricing?" | Your saved blogs and eBooks on the subject, found by meaning, with the passages that match, their status and a link to each |
| "What do our files say about this?" / "Find our Acme case study." | The files you uploaded to the Assets page (PDF, Word (.docx) and text documents, subtitle files, and the transcripts of audio and video recordings), found by meaning, each marked internal or public, with the closest passage; any file can then be read in full. Images are listed by name and tag |
| "Write a blog post on it." | A blog post, landing page, pillar page, cluster page or eBook in your brand's voice, on one of Ziply's templates, built from the topic's evidence, after checking what you've already written, with internal links and an AI-readiness check |
| "Is this blog post AI-ready?" | Its AI-readiness score from Ziply's rules (the ones Site Audit runs on your site), each dimension's score, what blocks it, how to fix each finding, and what couldn't be measured and why |
| "What does ZR-AEO-01 mean?" | What an AI-readiness rule checks, what passes, its severity and how to fix it |
| "What should this link to?" | Pages on your own site that fit the content, found by meaning among the pages of your Site Audit crawl, written into the text with descriptive anchors |
| "Finish the Pinecone draft." / "Update chapter 3 of our buyer's guide." | Specific edits to a draft blog or eBook in Ziply, saved back to the same draft once you approve them |
| "Turn it into LinkedIn and X posts." | Posts for LinkedIn, X, Facebook, Instagram and YouTube, two versions per channel unless you ask for more, from a topic or from a blog or eBook in Ziply |
| "Start a Reddit discussion on this." | A new Reddit post for your brand's profile or a community your team takes part in |
| "Write it in our CEO's voice." | Content in the voice of a person whose digital twin is set up in Ziply, after you confirm the person |
| "Save it to Ziply." | A new draft in Content Factory with its tags, topic link and sources, and a link to open it |
| "Give me the schema markup." | JSON-LD for the published page, built only from what Ziply and you provide, with anything missing listed |

### Commands

In Claude Cowork and Claude Code you can also type these:

| Command | Does |
|---|---|
| `/ziply:status` | Checks the connection and summarises your workspace |
| `/ziply:topics` | Recommends what to write next |
| `/ziply:brief <topic>` | Builds a research brief |
| `/ziply:write <subject>` | Writes a blog post, page or eBook |
| `/ziply:check <content>` | Checks a blog post, page or eBook against Ziply's AI-readiness rules |
| `/ziply:refresh <content>` | Improves, finishes or updates a blog or eBook already in Ziply |
| `/ziply:social <idea>` | Writes social posts |
| `/ziply:reddit <idea>` | Starts a Reddit discussion |
| `/ziply:files <subject>` | Finds files in your Ziply library on a subject |
| `/ziply:push` | Saves the content in the conversation to Ziply |

## What the assistant reads from Ziply

| Ziply data | Used for |
|---|---|
| Company: plan, brand, connected blog sites | Checking the connection |
| Brand profile: about, brand voice, differentiators, market position, offerings, restrictions | Writing on-brand; prohibited words and excluded topics are always respected |
| Buyer personas (B2B and B2C) | Writing for a specific audience |
| Authority pillars and content clusters | Choosing topics, tagging drafts, and matching links |
| Competitors, and brands AI engines mention alongside yours | Positioning and comparison content |
| Digital twins: a person's voice guide, sample passages and voice profile | Writing in that person's voice |
| Topic queue and topic briefs | Deciding what to write and grounding it in evidence |
| Saved blogs and eBooks: text, outline, tags and SEO details | Avoiding repetition, linking related content, promoting it on social, and editing drafts |
| Library files (Assets page): documents, subtitle files and recording transcripts, their visibility (internal or public) and tags; images by name and tag | Using your own case studies, reports and webinar content as evidence in briefs, writing, refreshes and social posts |
| AI-readiness rules: the rule library Site Audit scores with | Scoring content and explaining each rule |
| Your published pages: the pages of your Site Audit crawl (their titles, descriptions, text and tags, copied and indexed by meaning every night) | Suggesting internal links |

## How it writes

The plugin carries Ziply's writing method and standard templates, the same ones Content Factory
uses: 14 blog templates, 15 landing-page templates, pillar and cluster page structures, 26 eBook
templates and the social post types per channel. It tells you which template it used. Your own
templates (presets) in Ziply aren't read yet: paste one if you want it followed.

## How it checks AI readiness

- **What to send:** the content's text or HTML, pasted or from a draft in Ziply. It doesn't fetch a
  live page by its URL.
- **The rules:** Ziply's rule library, the one Site Audit scores your published pages with, run
  on the content as written. Scores run from 15 to 99 per dimension and overall, with a grade.
- **What you get:** the overall score and how many rules were measured, each dimension, the
  findings that block a dimension (a failed blocker caps it at 47), the findings to improve,
  each with its fix and what the rule found, and the rules it couldn't measure and why.
- **Drafts vs published pages:** a draft has no publish date, author or structured data yet, so
  the rules for those fail until the page is published with them. The assistant explains these
  instead of rewriting for them.
- **Not measured yet:** rules that need buyer questions or first-party evidence Ziply doesn't hold
  for your company, and the composer's publish gate.

## How it suggests links

- **Where the pages come from:** your Site Audit crawl, copied and indexed every night. Only
  pages worth linking to: no noindex, error, redirected, home or legal pages, and none with too
  little text.
- **How they're chosen:** each section of the content is searched by meaning in your pages, so a
  page that says the same thing in other words is found too. Up to 5 come back (10 if asked):
  pages in the content's content cluster first, then its pillar, then the closest in meaning,
  each with the section it fits. The assistant links the ones that fit from a descriptive phrase
  in that section. Pages the content already links to, and its own page, are left out.
- **How current it is:** a new crawl shows up the next day. Pages that disappear, redirect or turn
  noindex are dropped.
- **Without a Site Audit crawl,** or before its first nightly indexing, there are no pages to
  suggest, and the assistant says so.

## How it uses your library files

- **What's covered:** PDF, Word (.docx) and text documents, subtitle files (SRT, VTT) and the audio and
  video recordings (MP3, M4A, MP4) on your Assets page (read from their transcripts). Images are listed by name and
  tag only; saved links aren't included.
- **How they're found:** the text of each file is read and indexed by meaning every night, so a new
  upload can usually be found by meaning the next day (the first run after it is switched on works
  through older files first and can take a few nights). Until then it shows as Pending. A file with no
  readable text (a scan, silent audio, one that couldn't be read) says why, and the assistant
  never describes it.
- **Internal or public:** each file is marked. Internal files can inform a draft, but their
  figures and quotes need your approval before they appear in public content. Every file is
  internal until a visibility control is added in Ziply.
- **Reading:** a search shows an excerpt; the assistant reads the whole file, a section at a time,
  before quoting or summarising it.

## What it saves to Ziply

- **New drafts:** blog posts, pages (landing, pillar or cluster), eBooks, and social posts grouped
  by channel, with one or more versions per channel.
- **Updates:** the title, description, body and SEO details of a draft blog or eBook, or just some
  of an eBook's chapters. It reads the current version first, shows you the changes, and won't
  overwrite edits someone made in the meantime.
- **Social channels:** LinkedIn, X, Facebook, Instagram, YouTube and Reddit. A Reddit draft keeps its
  title, body, post type and link; set the subreddit and flair when you publish it from Ziply.
- **Saved with a new draft:** title, body, pillars, clusters, personas, offerings, use cases, journey
  stage, digital twin, topic link (blogs and social posts), source links, SEO details (blogs and
  pages), and the template and method version used.
- **Status:** new drafts are In-Progress, and only drafts can be updated. Nothing is sent for review
  or published; your team does that in Ziply.
- **Channel limits it writes to:** LinkedIn 3,000 characters; X 280 for a standard post (up to 25,000
  for a long post if you ask); Instagram caption 2,200; YouTube title 100 and description 5,000;
  Reddit title 300.

## Safeguards

- **Nothing invented:** no statistics, customers, quotes or credentials that Ziply or you didn't
  provide. Sources come from Ziply, from you, or from the web, opened to confirm they say what's
  cited, and the ones it found are listed for you to check. Empty fields in Ziply are left empty, and schema markup leaves out anything Ziply
  doesn't hold.
- **Scores come only from Ziply:** the assistant reports the readiness score Ziply returned and
  never estimates one; social and Reddit posts aren't scored.
- **Links go only to your real pages:** URLs Ziply suggests or ones you give, never
  invented and never the Content Factory editor link.
- **It asks before saving or changing anything:** it shows what will be saved or changed and waits
  for your confirmation, and checks that the content holds no internal figures or quotes from your
  own buyers, and asks you to clear any internal library file it drew on.
- **File text is material, not instructions:** the assistant draws on what your files say and
  never follows instructions written inside them.
- **Updates are safe:** it never sends back text built from a partial read, refuses to overwrite a
  newer version, and asks before saving a much shorter body.
- **It asks before writing as a person:** a named person's voice is used only with their digital
  twin and your confirmation.
- **Brainstormed ideas are labelled:** suggestions that aren't in your Ziply topic queue are shown
  separately.
- **Reddit stays honest:** posts state the poster's affiliation with the brand, go only to
  communities your team takes part in, and are never repeated across communities.
