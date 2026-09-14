---
layout: chapter
title: "The Pilot"
chapter_number: 21
permalink: "/chapters/21/"
prev: "/chapters/20/"
next: "/chapters/22/"
---

They rebuilt Escalation first, which Maya thought was either very brave or very obvious of them, and had come to understand, over three weeks of watching it happen, was probably both.

The new team was four people. Sam. Ruth, embedded now rather than consulted after the fact, with real authority to stop a change rather than merely flag one. Josh, still leading, though leading differently — Maya had watched him, twice, actually cancel a planned release because the team hadn't finished understanding something, and say so out loud in a standup, in front of people who reported to him, without flinching. And a fourth, quieter engineer Maya had barely spoken to, whose main qualification, as far as she could tell, was that he asked more questions than anyone else in the building and had simply never been on a team small enough for that to be welcomed before.

The friction arrived exactly where Marcus had told her it would.

"We're two days behind where we'd have been under the old process," Josh admitted, in a review Maya sat in on more out of habit than necessity by that point. "I want to be honest about that, because I think pretending otherwise helps nobody."

"Two days behind, or two days more honest?" Ruth asked, not unkindly — she asked most things not unkindly now, Maya had noticed, now that being asked things at all was no longer a fight she had to win first.

"Both, probably." Josh didn't sound defeated saying it, which was its own small victory. "I keep catching myself wanting the dashboard back. The green one. It told a cleaner story than this does."

"It told a story," Ruth said. "It just wasn't the true one."

"For what it's worth," she added, "we're not slower everywhere. Most of what this team's shipped this week was drafted by an agent in minutes and reviewed properly in twenty — routine work, well understood, low consequence if it's slightly wrong. Nobody's precious about using the tools for that. I'm certainly not. The two days went entirely into the one part of the system where getting it wrong nearly killed someone, and where none of us yet had the judgement to know we were getting it wrong. That's not the same decision, applied everywhere, out of caution. It's one decision, made correctly, about the one thing that actually needed it."

Josh looked at her for a moment, something in his shoulders coming down slightly, the way Sam's had, weeks ago, in a different conversation Josh didn't yet know about. "I think I'd stopped being able to tell the difference between those two kinds of decision. Everything just felt like the same amount of risk, because nothing was ever measured well enough to tell them apart."

"That's the actual job now," Ruth said. "Not slower. Not faster. Knowing, every time, which one you're looking at."

---

Maya found Sam later that week, not in the stairwell this time but at his desk, hunched over something that wasn't code — a whiteboard photo, blown up on his second monitor, covered in boxes and arrows in three different colours.

"What's this."

"Ruth asked me to design how we actually want patient-identity resolution to work. Not fix the old thing. Design the new thing, from scratch, properly — what should happen when a record's been merged, what a clinician actually needs to see when that happens, what questions the system should refuse to answer confidently if it isn't sure." He didn't look up immediately, absorbed in a way she hadn't seen from him since the first week, when the absorption had all been dread. "I spent two days just talking to the clinical safety team about how they actually think about risk. Nobody's ever asked me to do that before. I didn't know it was a thing I was allowed to spend two days doing."

"How does it feel?"

He considered the question properly, the way she'd noticed he did most things now — slower, more willing to sit inside a pause instead of rushing to fill it with an apology. "Different to how I thought it would. I thought getting good at this again would mean going back to writing more code myself, proving I could still do the thing I trained for. It's not that. I haven't typed more than forty lines this week, and the agent still wrote most of those, the same as it always would — I'm not trying to prove anything by doing it by hand. I've drawn about six diagrams and had maybe a dozen conversations with people who actually understand parts of this system I never will." Something that was almost a laugh. "I think I assumed the job I lost was 'writing code.' I'm starting to think the job I actually lost — and I'm getting back, slower than I expected — is deciding what matters. The code was just how it used to get expressed. It's not the only way it gets expressed. I just needed someone to tell me the deciding part still counted as the job."

"It's the only part that ever really was the job," Maya said. "The code was always just the shape understanding happened to take, for a while, because it was the only shape available."

Sam nodded slowly, and turned back to the whiteboard photo, and Maya watched him trace one of the boxes with his finger — not fast, not for show, just following the shape of something he'd actually built, on purpose, for a reason he could explain to anyone who asked.

"Someone told me last month," he said, not looking up, "that a man almost died because of code I shipped without understanding it. I think about that most days. I don't think I'll ever stop thinking about it, and I don't think I'm supposed to." He paused. "But I got an email yesterday. Clinical safety flagged three more records with the same historical merge pattern, using the check we built this week. Real patients. Real risk flags that would've gone quiet the old way. Nobody's going to write a headline about that. It's not going to show up on anybody's dashboard as a number that goes up." He looked at her then, and something in his face had settled into a shape she hadn't seen on him before — not happiness exactly, something steadier and more durable than that. "But I built the thing that caught it. Actually built it, understood it, could explain to you why every part of it is shaped the way it is. That's the first time since I got here that this job has felt like the thing I thought I was training for. It just doesn't look anything like I expected it to."

---

Maya reported the near-catch to Kalu that evening, mostly because he'd asked to be kept informed of anything that counted as good news, and there had been vanishingly little of that to offer him in three weeks.

"Three records," Kalu said. "That's it? That's the win?"

"That's three people whose risk flags didn't go quiet, this time, because a twenty-three-year-old who nearly lost his job over the last version of this exact mistake spent two days talking to clinicians about how they actually think, instead of two hours prompting a tool to make the ticket disappear." Maya looked out at the building, lit up floor by floor against the evening, and found she meant the next part more than she'd expected to when she started the sentence. "I've spent four weeks writing you a report about a catastrophic failure, Mr Kalu. That's the only line in it I actually want on a wall somewhere."
