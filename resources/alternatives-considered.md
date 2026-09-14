# Alternatives considered

A reference bank of structural and teaching-vehicle ideas that were explored but not chosen — kept here rather than discarded, since several remain good sources of secondary-character or subplot material. Split out of `writing-plan.md` on 2026-09-11 to keep that file lean, now that the book has a single settled structure (§3) and teaching vehicle (§4a) with no need to keep comparing against roads not taken.

## Alternative story structures

Three candidate four-act structures were drafted, all on the confirmed crisis → diagnosis → transformation → distilled-lesson arc. The one actually used is described in `writing-plan.md` §3. The other two:

### "The Programme" (single team, procedural)

The most direct reading of the premise: one protagonist, one struggling programme, a linear diagnosis. Closest in shape to Bill Palmer's own arc in *The Phoenix Project*.

- **Act 1 — The crisis (arrival):** The protagonist is dropped into a programme that looks, from the outside, like an AI success story — huge output, leadership excited — but is quietly failing. Early scenes establish wildly uneven personal AI usage (some engineers running up bills that would embarrass a manager, others barely touching the tools) and a hardening faction who've opted out of AI on patient-facing work as a matter of conscience (*theme 1*, principled-refusal strand fictional), a ballooning and unaccounted-for AI spend already drawing leadership's attention (*theme 2*), and a backlog full of impressive-looking but low-value AI-generated work next to core deliverables that haven't actually sped up. Mandate: fix it, fast.
- **Act 2 — The diagnosis (things get worse before they get clearer):** Codebases across teams have quietly drifted apart (*theme 3*); review has silently stopped working (*theme 4*); a flood of AI-written ADRs/PR summaries look rigorous but don't hold up to scrutiny (*theme 5*); a skills/prompt-library sprawl with no way to tell if a change helped (*theme 6*). The mentor figure appears here, teaching through questions rather than answers. A near-miss security incident (*theme 7*) — caught, not catastrophic — is the first sign the dysfunction has real teeth.
- **Act 3 — The reckoning (the crunch point):** Leadership finally asks what all this AI spend is actually buying (*theme 2*, forced into the open). The protagonist proposes what looks like a demotion in ambition but is the real fix: break the large siloed teams into small, empowered, co-located units (*theme 8*). The refusal thread comes to a head — the protagonist has to actually engage with the AI-refusing engineers rather than route around them, and finds their instinct is legitimate safety-critical caution, not Luddism. A human/career subplot (junior onboarding, senior burnout) runs alongside (*theme 9*).
- **Act 4 — The turn:** The restructure is piloted on one slice of the programme and works — not because AI got better, but because the organisation around it changed shape. Leadership scales it; the programme survives. Closing chapter: the distilled framework.

### "Three Pods" (ensemble, ecosystem-scale)

Widens the canvas the way *The Phoenix Project* itself does (Manufacturing/IT Ops/Retail as parallel fronts), rather than following one team closely. The protagonist inherits three semi-autonomous pods within the healthcare group's programme, each embodying a different failure mode in its most extreme form — useful if the book wants more named characters and a bigger ensemble than the chosen structure supports. Would have required the protagonist's mandate to be cross-programme (a "fix the whole portfolio" role) rather than one team.

- **Act 1 — The crisis (arrival):** Three pods, three flavours of the same disease, introduced almost as separate short case studies: **Pod Velocity** is burning enormous, unaccounted AI spend chasing volume (*themes 1, 2*); **Pod Legacy** is drowning in codebase drift, unreadable AI documentation, and review that quietly stopped meaning anything (*themes 3, 4, 5, 6*); **Pod Caution** is where the principled AI-refusers have concentrated, shipping slowly but safely, resented by the other two for "holding the programme back." Leadership wants one unified fix across all three.
- **Act 2 — The diagnosis:** The protagonist (and mentor) discover the three pods aren't actually different problems — they're the same organisational failure (large teams, unclear ownership, no shared feedback loop) expressing itself differently under different local pressures. A security incident (*theme 7*) originates in Pod Velocity's rushed code but is initially blamed on Pod Caution's slower, "unfashionable" process — a misdiagnosis the protagonist has to correct, which is itself a lesson about how organisations assign blame.
- **Act 3 — The reckoning:** The incident forces a portfolio-wide reckoning on cost and risk together (*theme 2*, *theme 7*). Rather than picking a winning pod, the protagonist redesigns all three into small, empowered, mixed teams that combine what each pod got right — Velocity's comfort with the tools, Legacy's hard-won architectural scars, Caution's risk discipline (*theme 8*). Pod Caution's engineers become the safety-review backbone of the new structure rather than an obstacle to it, resolving the resentment. A junior/burnout subplot (*theme 9*) plays out across at least two pods for contrast.
- **Act 4 — The turn:** The blended small-team model is piloted across the merged pods and outperforms all three originals. The open-source subplot (*theme 10*) and a "software for one" grace note (*theme 11*) can live naturally here as one engineer's side project that seeds the new way of working. Closing chapter: the distilled framework, framed explicitly as "what each pod was missing that the others had."

### Comparing the three

| | Scope | Pace | Best fit if... |
|---|---|---|---|
| The Programme | One team | Slow-burn turnaround | You want the closest match to *The Phoenix Project*'s own shape and a tight, focused cast. |
| Three Pods | Portfolio-wide, ensemble | Slow-burn, wider canvas | You want a bigger cast and room for themes 10–11 (open source, software-for-one) to breathe as genuine subplots rather than grace notes. |
| **The Incident (chosen — see `writing-plan.md` §3)** | One team, investigation-framed | Fast, thriller-paced | You want urgency and higher stakes from page one. |

All three end on the same distilled framework — they differ in how the reader arrives there, not in the "moral" itself. "Three Pods" in particular remains a source of ideas: its device could still supply secondary characters or a subplot inside the chosen investigation (e.g. Josh Whitfield's team being split into two contrasting pods), and "The Programme"'s slower diagnosis beats are useful texture for the investigation's Act 2 scenes.

## Alternative teaching vehicles

*The Phoenix Project* has Erik take Bill to walk a manufacturing plant floor, making Theory of Constraints physically visible. Five candidate equivalents were drafted for Marcus to use with Maya; the one actually used (a kitchen, developed with East Asian culinary philosophy) is described in `writing-plan.md` §4a. The other four:

### The hospital's own M&M conference (Morbidity & Mortality review)

The vehicle doesn't require leaving the building: this healthcare group already runs Morbidity & Mortality reviews and WHO-style surgical safety checklists, because clinical practice solved a version of this exact problem decades ago. Marcus gets Maya into an M&M meeting (or a pre-surgery "time-out") and she watches clinicians dissect a bad outcome without naming a culprit — every question aimed at "what about the system let this happen," never "who screwed up." The dramatic irony does the work for you: the organisation didn't need to invent a blameless, structural investigation culture, it already had one, one floor away from the engineers who needed it. Best fit: theme 7 (safety), the moral itself (prevention over blame), and it's the natural place to foreshadow Ruth Okafor's vindication — a "Just Culture" model would have protected her instead of sidelining her. Strongest option for staying inside the novella's page budget, since it costs no travel and no new named characters. **Still a strong candidate** for a single light touchpoint elsewhere in the book (e.g. Maya noticing the hospital's own blameless-review culture in passing during the investigation) without needing to be staged as a full scene, if a second, darker-toned counterpoint to the kitchen vehicle is wanted later.

### Wildland firefighting and the Mann Gulch collapse

Organisational psychologist Karl Weick's real study of the 1949 Mann Gulch fire ("The Collapse of Sensemaking in Organizations") is about a firefighting crew whose role structure and communication literally dissolved once things got fast and chaotic — people stopped checking in with each other and started acting alone, with fatal results. That's an almost exact structural echo of a real line from the interviews: "people aren't seeking human assistance early; they're almost going off on their own into it." Marcus could introduce this via a retired smokejumper or incident-command trainer he knows, or simply teach the case study directly. Best fit: theme 3 (review breaking down, going it alone) and theme 8 (team structure/role clarity). Intellectually the richest and most quotable option, but costs pages — probably needs a secondary character or a scene of its own, which is a real constraint at ~45,000 words.

### Aviation's black box and "Just Culture"

The classic analogy — CVR/FDR data-first investigation, no-blame incident reporting (the real-world ASRS), checklists, CRM — and it maps cleanly onto the idea that AI systems now generate their own "black box" traces nobody in the organisation has been treating with anything like aviation's rigour. Risk: this is already a well-worn analogy in tech/SRE circles, so it may read as less fresh — though that could be turned into a knowing beat, with Marcus himself acknowledging "everyone reaches for the aviation analogy" before explaining why he's using it anyway. Best fit: theme 7 (security/safety) and theme 6 (skills governance — aviation's rigorous, auditable change control is the opposite of an ungoverned skill silently degrading).

### Formula 1 pit crew and pit wall telemetry

Sub-two-second pit stops: extreme rehearsal, exact narrow roles, real-time telemetry-driven decisions, and no single person reviewing the whole job — plus a hard budget cap that forces real trade-off decisions, a neat echo of theme 2 (cost). Marcus shows Maya slow-motion footage of a stop and draws out how many independent, trusted, small-scoped actions combine into one outcome. Best fit: theme 8 (small teams) and theme 2 (cost as a forcing function). The highest-energy, most thriller-compatible option, but the weakest on the specific *blame/safety-culture* lesson the plot most needs — it's more about speed-with-precision than about how organisations investigate failure.

### Comparing the five

| | Best-fit theme(s) | Page cost | Main risk |
|---|---|---|---|
| M&M conference | 7, the moral, Ruth's arc | Lowest (no travel, no new characters) | Might feel *too* convenient/neat |
| Mann Gulch | 3, 8 | Highest (needs a new character or dedicated scene) | Richest lesson, but expensive at novella length |
| **Kitchen brigade (chosen — see `writing-plan.md` §4a)** | 8, 4 | Medium | — |
| Aviation black box | 7, 6 | Medium | Familiar/well-worn analogy |
| F1 pit crew | 8, 2 | Medium | Weakest on the blame/investigation lesson specifically |
