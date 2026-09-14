---
layout: chapter
title: "Kicking the Tyres"
chapter_number: 12
permalink: "/chapters/12/"
prev: "/chapters/11/"
next: "/chapters/13/"
---

The engineer who'd approved PR #4471 in four minutes turned out to be perfectly pleasant about explaining exactly how little those four minutes had involved, which Maya found more unsettling than if he'd been defensive about it.

"I check the tests are green. I check the diff isn't doing something weird to a dependency. If the review bot's flagged anything, I look at that specifically." He said it without embarrassment, because in his mind, reasonably, there was nothing to be embarrassed about — this was simply how the job was done now, the way everyone around him did it. "Reading four hundred lines of matching logic line by line would take me the best part of an hour. Nobody's got an hour per PR anymore. We ship twelve, fifteen a day across the team."

"Did the tests look thorough to you?" Maya asked.

"They looked like tests. Green ones." A small, honest shrug. "I'll be straight with you — I don't think I could tell you, looking at a test file, whether it was actually covering the cases that mattered, versus covering the cases that were easy to write. I'm not sure anyone can, quickly. That's sort of the problem, isn't it. The bit that used to slow you down enough to notice something was missing was reading the code closely enough to ask what it *wasn't* testing. Nobody reads it closely enough for that anymore. Including me."

"Would Ruth Okafor have caught it?"

Something shifted in his face — not defensiveness, more the specific discomfort of a man being asked to say a true thing about a colleague he liked. "Probably. Ruth catches everything. That's sort of her whole reputation." A pause. "She's not on our review rotation, though. She's Clinical Platform. We're Delivery. Different team, different backlog, different Slack channel most days."

"She wrote a formal warning about exactly this failure mode eleven months ago."

"I didn't know that." He said it plainly, and Maya believed him, which was somehow worse than if he'd been lying. "Nobody circulated that to us. I don't even know whose job it would've been to circulate it."

---

Marcus found the second half of it an hour later, in a request Ruth had filed six months after her original warning, buried in the same system as everything else that had quietly stopped being mentioned.

*Ruth Okafor: Requesting to be added as a mandatory reviewer on any change touching patient-identity or matching logic, across teams, given the risk profile documented in [link]. Happy to keep this lightweight — a notification and a 24-hour review window, not a blocker.*

*Josh Whitfield: Appreciate the offer, but adding a cross-team mandatory reviewer creates a dependency we can't always plan around, especially with delivery pressure the way it is. Let's revisit if we see actual issues.*

Six words did most of the damage, Maya thought. *If we see actual issues.* As though a formally documented, independently reproduced failure mode wasn't already one.

"He's not wrong that a mandatory cross-team reviewer creates friction," Marcus said, reading over her shoulder. "That's a real cost. I want you to notice that, because it's easy to make Josh a villain for saying a true thing badly timed. The actual failure isn't that he said no. It's that saying no to Ruth, specifically, on this, cost the organisation nothing visible for eleven months — until it cost them almost everything, all at once, on a Tuesday. Nobody built a way to feel the first kind of cost while it was still small and preventable. They only ever felt the second kind."

"So review didn't fail because people got lazy."

"Review failed because reading code slowly enough to catch what it *doesn't* do used to be the job, and it stopped being the job, quietly, for a genuinely defensible reason — there's more code, made faster, and nobody has more hours in the day to read it in. The tragedy isn't that anyone chose badly. It's that nobody chose at all. The old discipline just got out-run, and nothing was deliberately put in its place." Marcus straightened, already moving toward the door, already thinking about something else. "Find out one more thing for me. Whether anyone, anywhere in this building, still reads code the way that engineer described reading tests — closely enough to notice what's missing, not just what's there. If the answer's genuinely nobody, that's your headline. If the answer's one person, in one corner, doing it because nobody told her to stop — that's a better story, and I suspect you already know who it is."

Maya did. She'd known for two days. She just hadn't let herself say it yet, because saying it out loud made Ruth's isolation feel less like an oversight and more like something the building had done to her on purpose, one reasonable, individually defensible decision at a time.
