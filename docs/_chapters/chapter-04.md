---
layout: chapter
title: "The Team"
chapter_number: 4
permalink: "/chapters/04/"
prev: "/chapters/03/"
next: "/chapters/05/"
---

Josh Whitfield's floor didn't look like a floor in crisis. That was the first thing Maya noticed, and she noted it the way she noted everything on a first pass — not as a conclusion, just as a fact that would mean something later or wouldn't.

Nine desks, six occupied, headphones on, three separate video calls happening at a volume that suggested nobody had told this team to be quiet yet, which meant either nobody upstairs had told them how bad it was, or everybody upstairs already knew you couldn't stop a team like this mid-sprint without losing more than you saved.

Josh met her by the lifts. Late thirties, the specific tiredness of someone who'd been awake since a phone call at midnight and was covering it competently, which was its own kind of information.

"Maya Reyes. You're the—" he stopped, visibly deciding which word to use.

"Investigator. It's fine, you can say it."

"Investigator." He said it like a word he was trying on. "Right. Course. Where do you want to start?"

"Whoever touched the Escalation service's patient-matching logic most recently."

Something crossed his face — not guilt exactly, more the flinch of a man doing very fast mental arithmetic about who that was and how this was going to go for them. "That'd be Sam. He's — he's twenty-three, this is his first year out of uni, and before anyone in this building starts pointing at him, I want it on record that he was working exactly the ticket I gave him, in exactly the way this whole team works."

"Noted. I'd still like to talk to him."

Josh's jaw did something small and controlled. "He's had a rough eighteen hours."

"So has your patient."

That landed the way she'd meant it to — not cruelly, just precisely — and Josh nodded once, and took her over.

---

Sam Ilyas looked like he hadn't slept, because he hadn't. He stood up too fast when Josh introduced her, knocking his elbow on the desk, and said "sorry" to the desk before he said anything to Maya.

"You don't need to apologise to the furniture," Maya said, not unkindly, and something in his face loosened by about ten per cent, which she filed away — a kid who'd apologise to anything that would hold still long enough.

"I keep going over it," Sam said, before she'd asked a single question. "I keep thinking if I'd just — I don't know, read the old matching code more carefully before I touched it, instead of just clearing it out. The ticket had been sitting there two sprints, nobody wanted it, it's this horrible tangle of ID-lookup logic nobody's documented since before I joined, and I thought — I thought I'd tested it, I ran the test suite, it all passed, I don't—" He stopped, breathing harder than the sentence should have cost him. "Sorry. I know that's not useful. I keep saying sorry, I know that's not useful either."

"What did the test suite actually check?"

He blinked, like nobody had asked him that specific question yet, only variations of *whose fault is this.* "That lookups resolved correctly. Against — against the standard patient records. The ones in the fixtures."

"Did it check what happens for a patient whose record was merged with a duplicate, years ago — someone with an old ID still floating around somewhere in the history?"

A long pause. "I don't think there's a test for that. I didn't write one." His voice had gone very quiet. "I didn't even know that was a thing that could happen to a record. Is that — is that a thing I should have known?"

Maya didn't answer straight away, because the honest answer was complicated enough that giving it to a twenty-three-year-old two feet from tears at nine in the morning would have been its own kind of cruelty, and the dishonest answer — *no, don't worry about it* — would have been worse, because it wasn't true either.

"Who reviewed the pull request," she asked instead.

"One of the others on the team. Approved it in about four minutes. It's normal. We move fast here." He said it the way you'd repeat something you'd been told often enough that it had stopped sounding like an opinion and started sounding like a fact about the world. "The AI review bot flagged it as low risk. Style stuff, a couple of variable names. Nothing about — nothing about this."

"Did you read the code you shipped, Sam? All of it?"

He looked at her properly for the first time, and something in his face was younger than twenty-three, and older than it too. "I read what I wrote. Half of it I typed. The other half I asked Claude for, because that's how everyone does the boring bits now, and it looked — it looked right. It looked like code. I don't—" He stopped again, and this time the pause went somewhere she recognised, because she'd felt the shape of it herself, eight years ago, in a different building, over a different report. "I don't actually know if I could tell you why it's wrong. I know *that* it's wrong. I don't think I understand it well enough to know I should've been scared of it."

Maya wrote that down word for word, because it was, without either of them quite realising it yet, the single most important sentence anyone would say to her in the next eleven days.

"Get some sleep, Sam," she said, closing her notebook. "You didn't do this alone. I don't know yet who did, but I already know it wasn't just you."

He didn't look like he believed her. She didn't entirely blame him.
