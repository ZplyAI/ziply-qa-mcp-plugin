---
name: ziply-setup
description: Connects Ziply to this assistant and explains what it can do for the user's workspace. Use when the user asks to set up, connect, check or troubleshoot Ziply, when any Ziply tool reports that Ziply is not connected or not available on the plan, or the first time the user mentions Ziply in a conversation.
---

# Ziply setup

Ziply is the user's brand-authority platform. It holds their brand context, their topic queue, and the Content Factory where their blogs, eBooks and other drafts are saved. This skill confirms the connection works and tells the user plainly what they can do from here.

## Steps

1. Call `get_company`.
2. Act on what it returns:
   - **The Ziply tools aren't available, or a tool asks the user to sign in or reconnect.** Ziply is not authorised in this assistant. Tell the user to connect Ziply (in Claude: the Ziply plugin's **Connectors** tab, or `/mcp` in Claude Code; in ChatGPT: when it asks to connect) and sign in with their Ziply account. Don't call other Ziply tools until it's connected.
   - **`connectorEnabled: false`.** The company's plan doesn't include the assistant connector. Say so plainly: it's available on the Growth and Scale packages, with an active subscription. Don't suggest workarounds.
   - **Connected and enabled.** Summarise in a few sentences: the company and its plan, the brand by name, any connected blog sites, and what the user can ask for.
3. If a save later fails because the connection lacks the `content:write` permission, tell the user once: drafts can be written here, but saving or updating them in Ziply needs write access — reconnect Ziply and allow it. Until then, the push skill gives them a formatted export to paste into Ziply.

## What the user can do

Keep it short and concrete:

- **"What should we write next?"** Ranked topics from sales conversations, media and market intelligence, AI-visibility gaps and the team's own plans.
- **"Brief me on a topic."** Why it matters, the evidence and the sources behind it.
- **"Write it."** A blog post, page or eBook in the brand's voice, on Ziply's templates, after checking what the brand has already written.
- **"What have we already written about this?"** The brand's saved blogs and eBooks on a subject, found by meaning.
- **"Finish (or improve) the Pinecone draft."** Edits to a draft blog or eBook in Ziply, saved back after the user approves them.
- **"Turn it into LinkedIn and X posts."** Posts for one channel or several at once — LinkedIn, X, Facebook, Instagram, YouTube — with several variants each, in the brand's voice.
- **"Start a Reddit discussion on this topic."** A new post for the brand's Reddit profile or a community the team belongs to.
- **"Save it to Ziply."** As a new draft with its tags and topic link, or as changes to a draft blog or eBook.

## Not in this release

AI-readiness scores; reading or changing pages and social posts already in Ziply (they can be saved as new drafts); changing content that's in review or published (changes are saved as a new draft instead). Say so if asked, and offer what is available instead.

## Don't

- Promise publishing. This release saves and updates drafts; publishing happens in Ziply.
- Describe capabilities the plan doesn't include.
- Invent brands, sites or settings that `get_company` didn't return.
