# Chapter 6 — Too Much Ground

Maya got home to her flat in Kentish Town at half past eight. She ate toast standing at the kitchen counter, the way she did when a case had got hold of her, and opened her laptop on the counter beside the plate.

She typed the report first, because she always did. It was a discipline. You wrote the obvious answer down early so that you could see it plainly and test it, instead of letting it drift around unexamined and quietly decide things for you.

**Preliminary finding.** *On 12 January, a change to the Critical Results Escalation service (PR #4471) removed legacy logic responsible for resolving merged patient records. The change was made by a junior engineer using AI-assisted tooling, and was approved through standard code review. The logic was undocumented and untested, and its removal was not detected. On 23 February, a critical potassium result for a patient with a merged record was routed to a closed clinic inbox.*

*Contributing factors: insufficient understanding of legacy dependencies; inadequate review; absence of test coverage.*

It took her four minutes. It was accurate. She read it back and felt the familiar, slightly shameful click of a thing fitting.

Then she opened a new document beside it and typed, more slowly:

*R-117, raised eleven months before the incident, named this exact failure mode. It named the method and the mechanism, and said results would look delivered. It specified the mitigation and estimated the effort. The risk was downgraded, reassigned to a team, and scheduled behind feature work. A plain-English warning to the steering group was summarised by AI into a green bullet point reading "minor technical risk." The engineer who raised it was moved off the service.*

She looked at the two documents side by side.

The first was a story about a mistake, in which a person did something wrong and the organisation failed to stop them. The second was a story about an organisation that had been told, in writing, exactly what would happen, and had arranged itself in good faith so that the warning could never reach anyone with the power to act on it. Nobody had done anything wrong. Every process had worked as designed.

The first story could be closed. The second couldn't, because it didn't stop at Escalation.

She took her glasses off and sat down on a stool.

This was what she had been circling all afternoon in the small room in Paddington without quite saying it. If one warning had been buried this way, in one system, nothing about the mechanism was specific to Escalation. The risk register was the same for every service in Digital. So was the steering pack, and so was the summariser that turned nineteen papers into nine reassuring lines. Josh's team had been rewarded for velocity, and every team on that dashboard Felix loved had been rewarded for the same. The same tooling and the same internal Skills library were being used by six hundred engineers across two hundred services. Some of those engineers spent thousands a month on agents, a few had opted out entirely, and nobody had ever asked whether those two groups agreed about what was safe.

So the real question wasn't how this had happened. It was where else it was happening right now, and whether anyone had written it down.

That was not a fortnight's work for one person. It was probably not a fortnight's work for anyone. She had fourteen days until the board met. In that time she had to establish what had happened in Escalation, credibly enough to stand up in front of a regulator. She also had to establish whether the same thing was waiting in the other services, with their own buried warnings. And she had to do it while the chief executive, the chief digital officer and probably most of the board were hoping she'd come back with the four-minute version. She could do one of those things. She couldn't do all three alone.

Doing this properly meant someone else, she thought, and it meant a particular kind of someone. She needed a person whose whole career had been spent refusing to accept the plausible version. Someone who knew this failure, the way an organisation could write a warning down and then lose it in its own machinery, because they'd seen it before. Someone the board would find it harder to dismiss than her. Someone who would make her life more difficult in exactly the ways she suspected she needed.

There was one name that fitted, and she'd known what it was since about three o'clock.

---

She rang Graham first, because Marcus Kwan was not cheap and Kestrel would have to carry the cost until Meridian agreed to it.

"Marcus?" Graham said. She could hear a television in the background, and the clink of a glass being put down. "Maya, it's a two-week engagement. Ashworth wants a clean answer and she wants it fast. Marcus doesn't do clean or fast. Marcus does true, and then he writes a forty-page appendix about why your methodology was wrong."

"I know."

"The last time we put him in front of a board, the chair asked him whether he could just give a straight yes or no and he said, and I quote, 'I could, but you'd be paying me to lie to you.' We lost the follow-on work."

"I know, Graham. I was there."

"So why?"

She told him about R-117 and the slide. She heard the television go quiet.

"Christ," he said eventually.

"If I give them the four-minute version, they'll fire a twenty-four-year-old and buy some training. Six months from now, somebody else's warning about some other service will go green on a slide, and we'll be the firm that said it was a one-off." She paused. "I can't cover two hundred services in fourteen days. I need someone who's investigated this exact pattern before, and who'll stop me taking the easy answer when I'm tired. And I need someone Ashworth's board can't brush off."

There was a long silence.

"You realise," Graham said, "that you've just described yourself as a person who takes the easy answer when she's tired."

"Yes."

"In nine years I've never heard you say that."

"I've never said it out loud."

Another silence. Then Graham sighed, in the way that meant he'd lost and was quietly relieved about it.

"Ring him. If he says yes, I'll square it with Meridian on Monday. Tell him day rate, not his conference rate."

---

Marcus Kwan answered on the sixth ring, sounding as though he'd been interrupted in the middle of something and was deciding whether to forgive it.

"Maya Reyes," he said. "It's Friday night."

"I know. I'm sorry."

"You're not. You'd only ring on a Friday night if you weren't sorry." She heard a door close, and the background noise of a kitchen, a tap, a pan, faded. "Go on."

She told him, as concisely as she could. The result, the merge, the method removed in an afternoon by a junior using an agent and a Skill. The four-minute approval and the eleven-month-old risk. The slide. She found herself telling it in order and without adjectives, the way he'd taught her on the only other job they'd done together, six years ago. She noticed she was doing it and felt slightly foolish.

When she finished there was a pause on the line.

"And what do you think happened?" he said.

"I think the organisation was told exactly what would go wrong, and built itself in a way that made sure nobody who could act on it ever heard it properly."

"That's a nice sentence," Marcus said. "How do you know it?"

She opened her mouth.

"I've got the register entry," she said. "And the paper. And the slide."

"You've got three documents that say a warning existed and was downgraded. That isn't the same as knowing why. Maybe it was downgraded because someone looked at it carefully and made a reasonable judgement that the test coverage was adequate. Maybe the engineer who raised it raises forty of these a year and they're all wrong. Maybe the summariser was a once-off and every other slide is fine." He said it without any edge. He was simply listing the things she hadn't checked. "I'm not saying you're wrong. I'm saying you've found a very good story on day three and you should be suspicious of it for exactly that reason."

"That's why I'm ringing you."

"Is it?" There was a faint dry note in his voice. "I'd assumed you were ringing because you wanted someone to tell the chief executive it's structural, so it doesn't have to be you."

That landed closer than she liked. She didn't answer straight away, and he let the silence sit, which was very like him.

"Both," she said finally.

"Good. Honest." The tap ran again in the background and stopped. "What's the patient's name?"

"Desmond Hale. He's seventy-one. He's still in intensive care."

"And the engineer?"

"Sam Ilyas. He's twenty-four."

"And the one who wrote the warning?"

"Ruth Okafor."

He was quiet for a moment, and she had the odd impression that the name meant something to him. Not the person, but something about her.

"Is she still there?" he said.

"Yes. They've moved her to test tooling."

"Of course they have." He said it softly, almost to himself. Then, in his normal voice: "I'll come on Monday. Not before. I want to read everything first. Send me the register, the paper, the slide, the diff, the PR, the commit history for that module back to the beginning, and the incident timeline to the second. Don't summarise any of it. If you summarise it, I'll be reading your story instead of theirs."

"Graham says day rate."

"Graham always says day rate." She thought he might be smiling. "One more thing. Before Monday, don't decide anything. Not about the engineer, or the slide, or the chief executive. Just go and look at things and write down what you see."

"That's a very long weekend."

"It's a very long weekend for Mr Hale," Marcus said, and rang off.

Maya sat in her kitchen for a while afterwards. The rain had stopped. Somewhere across the road someone was having a party, and she could hear the bass of it through the window.

She went back to the laptop. The four-minute report was still there in the first window, neat and true and ready. She didn't delete it. She moved it into a folder and named the folder *What it looks like*, and then she created a second, empty folder beside it and named it *What it is*.

Then she started sending Marcus everything, unsummarised.
