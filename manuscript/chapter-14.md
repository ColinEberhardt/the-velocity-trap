# Chapter 14 — Nobody's Skill

*Draft — first pass.*

---

"I need to show you something," Tariq said, and Maya could tell from his voice, before she'd even looked up, that whatever it was had cost him something to bring to her rather than quietly fix himself.

He'd found it by accident, tracing which internal tooling Sam's session had actually used for the refactor — not the model, but the *skill*: a saved prompt template, sitting in Meridian's shared internal library under `legacy-simplify`, that engineers reached for whenever they were told to clean up old, unowned code.

"It's not originally ours," Tariq said. "I wrote the first version of this. Three years ago. Open source, on my own time — a prompt template for exactly this kind of job, safely modernising legacy code without an agent just bulldozing through it. It got a bit of traction. A few hundred stars, people used it, I forgot about it, mostly." He pulled up the original, side by side with Meridian's internal fork. "This is what I actually wrote."

*Before making any change that removes a code path, explicitly identify what historical case it might be handling. If you cannot determine this with confidence, do not remove it — flag it for human review and explain your uncertainty. Assume nothing about "dead" code without evidence it is actually dead in production.*

"And this," he said, "is what Meridian's internal version says now."

*Simplify legacy code paths to match current schema conventions. Remove redundant or superseded logic. Prioritise clarity and maintainability.*

The caution was simply gone. Not overridden, not debated — absent, the way a sentence is absent from a photocopy of a photocopy, one generation too far from the original to notice it was ever there.

"When did that happen?"

"I traced it through version history. Eight edits over fourteen months, by six different people, none of whom I think ever saw my original version — they were editing Meridian's copy of it, not mine. Someone flagged, five edits back, that the 'ask before removing' instruction was 'too chatty' and 'kept blocking simple cleanups with unnecessary questions.' Somebody else, two edits after that, trimmed it further for 'conciseness.' Nobody ran anything before or after any of those changes to check whether the skill still did what it used to do. There isn't a test for a prompt. There's no equivalent of a build going red. It just quietly got faster and more confident and less careful, one reasonable-sounding edit at a time, and the only proof any of it mattered is sitting in a coronary care unit."

"There's something else I want to be honest with you about," Tariq said, before she'd decided what to ask next, "because I think it matters more than the edit history does. Even my original version — caution and all — never made the agent *right*. It made it *better*. When I tested it, on a pile of old repos, it caught most of the risky-looking removals and flagged them instead of just doing them. Not all of them. Sometimes it still decided something was safe to delete when it wasn't, because underneath the caution it's still a model guessing at intent from whatever it can see, not someone who actually knows the history of the file. I said as much in the README, back when I wrote it. Nobody reads READMEs anymore, not really, but I did say it."

He turned the laptop slightly, as if the point needed a different angle to land.

"I think that's the part that actually got lost, more than the sentence itself. Not just the caution — the fact that following an instruction carefully doesn't make a probabilistic thing certain. It makes it *more likely to be right*, the same way a careful person following a good process is more likely to be right, and still sometimes isn't. The more times it worked here without an incident, the more everyone quietly started treating 'we ran it through the skill' as the same sentence as 'the risk was handled.' Nobody decided that on purpose. It's just what happens to a fact nobody's re-testing — it doesn't get argued away, it just stops being said out loud, until eventually nobody in the room remembers it was ever true in the first place."

Maya thought of the study Marcus had mentioned two days ago — a viral, unverified claim about a skill that was supposed to make code more concise, matched almost exactly by a three-word prompt when someone finally bothered to check. "Has anyone ever benchmarked whether an edit to this thing actually improved anything?"

"No. Nobody's ever benchmarked any edit to any shared skill here, as far as I can find. We test code. We've never built anything that tests the thing that writes the code — it never occurred to anyone that it needed testing, because it doesn't look like code. It looks like a paragraph of advice. Paragraphs of advice don't usually break production."

"This one did."

"This one did." Tariq said it quietly, and Maya understood, watching him, that the thing bothering him wasn't the incident itself — he'd had no hand in the incident itself — but the specific, private discomfort of finding his own name, three years and eight edits removed, standing somewhere underneath the wreckage of something he'd built to make this exact failure less likely, not more. "I put a safeguard into the world. Somebody else's organisation quietly filed the corners off it until it wasn't a safeguard anymore, and nobody, including me, was watching closely enough to notice it had happened."

"That's not on you."

"I know that, intellectually." He didn't look like he knew it anywhere else. "It doesn't change what it feels like to know a man nearly died, partly because of a caution I wrote in an evening, three years back, that got worn smooth by people who never knew my name and were only ever trying to make their Tuesday slightly easier."
