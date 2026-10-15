---
name: ziply-refresh-content
description: Improves, finishes or updates a blog post or eBook already saved in Ziply, such as completing a half-written draft, rewriting a section or chapter, updating outdated facts, tightening it or changing its title and SEO, by reading the current version, proposing specific edits and saving the approved ones back to the draft. Also finds and summarises what the brand has already written on a subject. Use whenever the user asks to finish, continue, edit, improve, rework, refresh, shorten, expand or fix content that's in Ziply, or asks what the company has already written about something.
---

# Refresh existing content

Refreshing starts from what exists: the current text, its version and its brief. Keep what works, change what needs changing, and keep the author's voice.

Blogs and eBooks only. Pages and social posts can't be read or changed from here yet: ask the user to paste the text, and save the result as a new draft.

## Steps

1. **Find it.** Use the content ID if the conversation has one; otherwise call `search_content` with its title or subject and let the user pick. Results show each piece's status: only **Draft** content can be saved back. For In Review or Ready content you can still propose changes, and save them as a new draft or have the user apply them in Ziply.
2. **Read it** with `get_content`, noting its `version`. Never work from a partial piece as if it were whole: if it comes back `truncated`, read the rest, and for a long eBook read the chapters you need with `chapters` (the outline lists them).
3. **Understand what it should be.** Load what it was written from: its topic brief (`get_topic_brief`, if it has a topic), the brand's voice and restrictions (`get_brand_profile`), its personas and pillar. For a blog or eBook, the write skill's method and templates apply to any new text (`ziply-write-ai-ready/references/`).
4. **Propose edits,** not a rewrite, unless the user asks for one:
   - **To finish a draft:** continue from where it stops, following its brief and its template's remaining sections.
   - **To improve it:** the answer first, sources attached to claims, headings buyers would ask, passages that stand alone, brand restrictions respected, links to related content (`search_content`).
   - **To update it:** facts, figures and dates that may be out of date. Flag anything that looks stale for the user to confirm; don't replace it with figures you can't source.
   Show each edit specifically (the section, the old text and the new), and say why.
5. **Apply what the user approves,** and nothing more.
6. **Save** through the push skill's *Update a draft* steps: the `version` from step 2, the whole new body (or just the changed eBook chapters with `chapters`), and the user's confirmation. If the draft changed since you read it, read it again and rebase the edits; don't overwrite.

## Questions about existing content

"What have we written about X?", "Do we have an eBook on Y?": answer with `search_content` (and `get_content` for detail), listing each piece's title, type, status and link, and what it covers. Say if nothing matched closely. Don't present search passages as the whole piece.

## Don't

- Rewrite beyond what the user approved.
- Replace the author's voice with a generic one.
- Send a body built from a truncated read, or drop chapters you didn't read.
- Give a readiness score; there isn't one in this release.
