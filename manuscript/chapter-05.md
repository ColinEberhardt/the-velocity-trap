# Chapter 5 — Buried

*Draft — first pass. Rewritten 2026-09-11: Ruth's warning is now specifically about AI-assisted rewrites of undocumented legacy code, not chatbot session-isolation — see the scope note in `writing-plan.md` §1.*

---

Kalu's team had given her a data room: four months of Confluence exports, Slack archives, PR history, incident tickets, all of it searchable, none of it organised around the question she actually had, which was *did anyone see this coming.*

She started with the obvious search terms — *matching, identity, merge, duplicate, legacy* — and got two hundred results, most of them noise. She was three hours in, eyes gone dry from the screen, when she tried *risk* instead, and narrowed by author, and found a name that hadn't come up anywhere else yet.

**Ruth Okafor. Principal Engineer, Clinical Platform.**

A design review document, filed eleven months ago, four months before anyone had called the identity-matching cleanup part of the Platform Modernisation initiative. Twelve pages. Maya read the executive summary twice before she understood she was reading a warning, not a proposal.

*Recommendation: do not proceed with AI-assisted simplification of the legacy patient-matching module until every historical edge case it currently handles has been documented and covered by tests — in particular, merged and duplicate patient records, which the existing code handles through undocumented special-case branches nobody currently working here has fully explained to me. An AI-assisted rewrite will produce clean, plausible code for the schema as it exists today. It has no way to know what the ugly branches were quietly protecting against, because nobody wrote that down, and it cannot ask. Risk: silent loss of correct matching for any patient whose record has ever been merged — an unknown but non-trivial population — whose active clinical risk flags may then fail to resolve. This is not a theoretical risk; see attached reproduction, section 4.*

There was a reproduction. Ruth had built one. Eleven months ago, on her own initiative, she had recreated the exact failure mode that had left a critical result unescalated for nine days, and she had written it up formally enough that it read, now, like a coroner's report written in advance.

Maya scrolled to the comment thread.

*Felix Adeyemi: Thanks Ruth — really thorough as always. Can we get a lighter-weight version of this for the steering group? I want us focused on the modernisation roadmap, not blocking it on edge cases we can harden later.*

*Ruth Okafor: This isn't an edge case, it's a known population of real patients — anyone whose record was ever merged after a duplicate registration, which happens more than people think. I can do the lightweight version but I don't want the risk itself softened in translation.*

*Felix Adeyemi: Understood, appreciate the diligence. Let's revisit post-launch once we've got the simplification live and can prioritise against real data.*

Nine replies down, a different name: **Josh Whitfield.**

*Josh Whitfield: Sorry Ruth, appreciate this but we're already behind on the roadmap for this quarter and documenting every historical branch before we touch it isn't something I've got headroom for. Can we park it and reassess in Q3? The AI tooling should make the actual rewrite quick once we're ready — it's the documentation-first approach that's the bottleneck, not the code.*

Attached to Felix's reply was a link — *Steering Group Pack, Q2 — Risk Register (auto-summarised)* — the kind of document that existed to be skimmed rather than read, which was presumably why nobody had thought to mention it existed until Maya found it herself. Ruth's lightweight version was in there, three honest paragraphs, still recognisably itself: risk of undetected clinical harm from unreviewed legacy code, recommend documentation and test coverage before further simplification. Somewhere between that draft and the steering pack, someone had run the whole risk register through a summarisation tool to fit it on one slide, and what had come out the other side, item eleven of nineteen, read: *Platform Modernisation: minor technical risk identified, team mitigation in progress, no committee action required.*

Fourteen words. Every one of them technically defensible. None of them true in the way that mattered. Ruth's sentence had survived Felix's inbox and died in a tool that had been asked to make nineteen different risks fit on a slide, and had done exactly that, because making things shorter was the only thing anyone had ever asked it to do.

Q3 had come and gone. The rewrite had shipped six weeks before the incident, on schedule, without the documentation Ruth had asked for ever being written. Nobody, in nine months of comment threads, had ever formally closed the risk, downgraded it, or accepted it in writing. It had simply stopped being mentioned, the way things do in organisations, not through a decision but through the absence of one — every day it wasn't fixed becoming, invisibly, one more day it had been quietly decided not to be.

Maya sat back, and for a moment did not move at all.

She pulled Ruth's staff record next, because she already suspected what she'd find and wanted to see it in the organisation's own words rather than her own inference. Fifteen years in medical device firmware before Meridian — pacemaker and infusion pump software, the kind of engineering where a design flaw showed up in a coroner's inquest rather than a retro. Two performance reviews since joining Meridian's software side, both average, one manager's comment flagged in bold by whoever had compiled this file for her: *Ruth's technical judgement is not in question. She can, at times, be an obstacle to pace, and colleagues have found her risk framing difficult to action against delivery deadlines.*

*An obstacle to pace.* Maya read it three times.

She thought about Sam, twenty-three, apologising to a desk, saying *I don't think I understand it well enough to know I should've been scared of it.* And she thought about Ruth Okafor, fifteen years and a specification document and a working reproduction, who had understood it exactly well enough to be scared of it, in writing, on the record, eleven months before anyone else in the building had to be.

One of them had been ignored for being too slow to trust with the truth. The other had been trusted with something he didn't yet have the years to see the shape of. Somewhere between those two people was the actual failure, and it wasn't a person at all.

She sat with that for a long time after the office had emptied out, the data room's cursor blinking at her in an otherwise dark screen, and admitted to herself, quietly, that she had seen this shape once before — not this incident, not this company, but this exact shape, the ignored warning and the unprepared hand and the space of blame in between them, waiting for someone to fill it with a name. She had filled it once, a long time ago, and had spent eight years telling herself she'd done the job correctly.

She was not going to do that again. She just didn't yet know what doing it properly would cost her.
