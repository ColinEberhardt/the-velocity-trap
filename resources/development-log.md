# The Velocity Trap — a Phoenix Project for the AI age

A business fable novella — same shape as Gene Kim's *The Phoenix Project*, new plot, shorter form — dramatizing what actually happens when AI coding agents hit real software delivery organisations. Written for external thought leadership: a standalone piece for engineering leaders anywhere (not Scott-Logic-branded), in the tradition of the DevOps/SRE/Lean business-fable genre (*The Phoenix Project*, *The Unicorn Project*, *The Goal*).

## Status

**Full first-pass manuscript complete (2026-09-11) — all 24 chapters drafted, consistency-checked, and now readable as a website.** See [`../manuscript/`](../manuscript/) for the source, and [`../docs/`](../docs/) for a minimal Jekyll site that renders it as a book (chapter 1 styled as an incident report, everything else book-style prose with a small ⁂ flourish marking scene breaks) — see `../docs/README.md` for local preview and GitHub Pages deployment instructions. Total length as drafted is ~22,000 words, well short of the ~45,000-word target in `writing-plan.md` §1 — the next real decision is whether to expand the existing draft or accept a shorter novella as the right length now that it exists as a whole. Everything upstream of drafting (premise, research, outline/structure, character roster with backstory, length target, teaching-vehicle metaphor, chapter-level beat sheet) is also done. **Important scope note baked into `writing-plan.md` §1:** the incident is a failure in an ordinary, unglamorous internal system (not Meridian's AI chat/triage product) — see below.

## Why this format

*The Phoenix Project* worked because it let a technical audience absorb an unfamiliar set of ideas (DevOps, the Three Ways, flow) through a protagonist's lived experience rather than a manifesto. The AI-age equivalent needs the same trick: the real tensions playing out right now in AI-assisted delivery are subtle, political, and easy to state as bullet points but hard to *feel* — this format is for making them felt.

## Source material

See [`source-material.md`](source-material.md) for the full idea bank: real practitioner interviews, Colin's own published thinking (`the-future-of-software-development.md`), and 14 months of his weekly newsletter (`newsletter-themes.md`) — not to transcribe verbatim, but to make sure every dramatized tension traces back to something real. The resulting [`themes-to-dramatize.md`](themes-to-dramatize.md) (11 themes) is what the plot and mentor-figure dialogue should be built against.

## Characters

See [`characters.md`](characters.md) for the full core cast (9 named characters), including a backstory/voice pass for the four who carry most of the book (Maya, Marcus, Ruth, Sam) and lighter touch-ups for the rest — split out of `writing-plan.md` once character development grew past a quick sketch.

## How a novel like this typically gets written

See [`novel-writing-process.md`](novel-writing-process.md) for the general stages (premise → research → outline → drafting → revision → editing → beta feedback → proofread → publish). [`writing-plan.md`](writing-plan.md) is this project's working document against those stages — everything through the chapter-level beat sheet (§4b) is done; drafting actual prose (§5) is next. [`alternatives-considered.md`](alternatives-considered.md) holds the structures and teaching vehicles that were explored but not chosen, kept as a reference bank rather than in `writing-plan.md` itself, to keep that file lean now the book has a single settled shape.

## Open questions

- Character names (still placeholders in `characters.md`, easy to change, deliberately not left undecided). The book's title is settled: **The Velocity Trap**.
- Whether to fold in more source interviews before locking the plot, or draft against what we have now.
- Whether any beats from the alternative structures/vehicles explored (kept in [`alternatives-considered.md`](alternatives-considered.md), not discarded) should be folded into the chapter-level detail — e.g. the "three pods" device as a source of secondary characters (`characters.md` notes Josh Whitfield's team as the natural place to do this later), or the M&M-conference idea as a single lighter touchpoint alongside the chosen kitchen vehicle.
- Whether the chapter-24 draft's closing framework ("Five things I wish someone had made me write down before my first one" — see `../manuscript/chapter-24.md`) is the right resolution to the earlier open question about Colin's "Future of Software Development" principles, or needs further alignment with them.

## Next steps

1. Read the full draft — either `../manuscript/` or via `../docs/` (`bundle exec jekyll serve` from that folder) — start to finish as one piece; everything so far has been reviewed chapter by chapter, not as a whole book.
2. Decide on length: expand the existing ~22,000-word draft toward the ~45,000-word target (more scene, more interiority, possibly splitting some chapters), or deliberately shorten the target instead — see `writing-plan.md` §5's milestone note.
3. Move into revision proper (`writing-plan.md` §6) once the length question is settled — structural/developmental edit, then line editing, then beta feedback.
4. **`../manuscript/` is still the canonical source; `../docs/_chapters/` is generated from it and not auto-synced** — if you redraft a chapter in `../manuscript/`, remember to update the corresponding file in `../docs/_chapters/` too (see `../docs/README.md`).
5. Deploy: `../docs/` needs to sit at the root of whatever repo GitHub Pages serves from — it can't stay nested here. See `../docs/README.md` for the two ways to do that.
