# How this novella was written

A step-by-step account of the process behind *The Velocity Trap*, written almost entirely by AI (Claude) under Colin's direction. The general stages this followed are laid out in [`resources/novel-writing-process.md`](resources/novel-writing-process.md); this document is the specific record of how those stages actually played out for this book. [`resources/development-log.md`](resources/development-log.md) is the fuller working log kept throughout.

## 1. Premise and audience

Started from a single brief: write something "similar to The Phoenix Project, but for the AI age." Format decided early — same shape as the source (a business fable, dramatizing real tensions through a protagonist's lived experience), new plot, written for external thought leadership rather than as an internal or company-branded piece.

## 2. Source material

Before inventing anything, gathered what was already known to be true, so that every dramatized tension would trace back to something real rather than an invented strawman. Three sources, catalogued in [`resources/source-material.md`](resources/source-material.md):

- A recorded practitioner discussion with Scott Logic consultants describing live AI-assisted delivery across real client engagements.
- Colin's own presentation, "The Future of Software Development" ([`resources/the-future-of-software-development.md`](resources/the-future-of-software-development.md)), which independently arrived at several of the same conclusions.
- 14 months of Colin's weekly newsletter, *Augmented Coding Weekly*, reviewed and distilled into [`resources/newsletter-themes.md`](resources/newsletter-themes.md) — a longitudinal record of how the industry's (and Colin's own) thinking moved over time, not just a single snapshot.

## 3. Themes

The source material was distilled into [`resources/themes-to-dramatize.md`](resources/themes-to-dramatize.md) — a numbered list of the specific tensions the plot needed to hit (cost, review quality, the erosion of judgement, the usage divide between engineers, and others). This list was revised twice during drafting: cost was promoted to priority 2 as its significance became clearer, and an early "tool access as politics" framing was replaced with a truer one — that the divide in AI usage is driven by personal preference, skill level, and principle, not access or politics.

## 4. Structure

Three candidate four-act structures were drafted as full outlines. Colin chose one — "crisis → diagnosis → transformation → distilled lesson," built around a specific incident investigation — and it became the book's only structure from that point on. The two unchosen alternatives (including a different teaching vehicle) weren't discarded; they're kept as a reference bank in [`resources/alternatives-considered.md`](resources/alternatives-considered.md) in case any of their beats were worth folding in later.

## 5. Characters

A nine-person core cast was developed with backstory and voice, recorded in [`resources/characters.md`](resources/characters.md): Maya Reyes, the external investigator whose own flaw (a preference for a clean, closeable answer over a harder true one) drives her arc; her mentor Marcus Kwan; the incident's human cost, junior engineer Sam Ilyas; and the executives, engineers, and whistleblower around them. The teaching vehicle — a small, exceptional restaurant, **Shun**, run by chef-owner Aiko Sato — was chosen to dramatize craft, apprenticeship, and deliberate practice without stating any of it directly.

## 6. Drafting

Prose was drafted chapter by chapter, in chunks, with Colin reading and reacting to each one before the next was written. Two things shaped this stage more than anything else:

- **Reverse-outlining from the ending.** Chapter 24 — the closing "five things I wish someone had told me" framework — was drafted first, so the rest of the book could be built toward a known landing point rather than discovered on the way.
- **A scope correction.** Early drafts of chapters 1–6 made the incident a failure inside the company's AI *product*. Colin caught that this confused the book's actual subject — AI as an engineering tool, not AI as a product feature — and chapters 1–6 were rewritten around a mundane, non-AI internal system failure instead. This distinction was recorded permanently in [`resources/writing-plan.md`](resources/writing-plan.md) §1 to prevent it recurring later in the book.

Colin steered several specific beats during drafting, all tracked in [`resources/writing-plan.md`](resources/writing-plan.md): softening an early interrogation scene, working in a moment of AI-summarised findings losing the point, correcting a misquoted detail, and — in the last act — making sure the ending shows a team that has adapted to AI rather than either resigning to blind speed or retreating into blanket caution.

## 7. Thematic threads

Beyond the scene-by-scene notes, three larger threads were deliberately woven across the whole book rather than confined to one chapter:

- Sam Ilyas used as a way of surfacing a collective unease across the whole engineering function, not just his own mistake — seeded in chapter 11, paid off in chapter 18.
- The idea that reading AI-generated code isn't the same as building judgement through slow, deliberate practice — landed explicitly in chapter 17, tied back to chapter 9.
- The engineering team rediscovering joy in Act 4 — not because engineering disappeared, but because it relocated to architecture, judgement, and taste, with product impact as its own source of meaning.

## 8. Consistency review

Once all 24 chapters existed, the full manuscript was read as a whole for the first time and checked for consistency in plot, characters, and timeline. This caught and fixed a drifting day-countdown across several chapters, a misattributed decision, and a confusing line of dialogue. Two larger issues were deliberately *not* patched over with a contrived fictional fix — instead, Colin's own steer was followed: naming the still-unsolved problem explicitly on the page, and having the board grant institutional cover to keep working on it, rather than pretending it was solved.

## 9. The author's note

Colin wrote his own prologue — an author's note on AI's impact on the software industry, citing *The Phoenix Project* as direct inspiration, with a candid disclaimer about the book's own AI-assisted authorship (see [`manuscript/prologue.md`](manuscript/prologue.md)). It received a light copyedit and was placed ahead of chapter 1 as "Before We Begin," with Colin's own sign-off.

## 10. Publishing

A Jekyll site was built to present the finished manuscript as a book rather than loose markdown files: an off-white, book-styled layout for most chapters, a deliberately distinct monospace "incident report" style for chapter 1, and a small ⁂ flourish marking scene breaks. Colin supplied the cover graphic used on the homepage. The site lives in [`docs/`](docs/) and is published via GitHub Pages directly from that folder.
