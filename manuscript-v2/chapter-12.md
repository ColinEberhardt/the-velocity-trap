# Chapter 12 — Kick the Tyres

On Thursday morning, before King's Cross, Maya went to Kingsgate.

Kalu had arranged it. The hospital's surgical department held its morbidity and mortality meeting on the first Thursday of the month, and that month the first case on the list was Desmond Hale. She sat at the back of a lecture theatre with tiered seats and a projector that hummed. For an hour she watched forty clinicians take apart what had happened to him.

She had expected it to feel like a trial. It didn't. The consultant chairing it laid out the timeline slide by slide, in the same flat, careful language Helen Marsh had used in her statement. Then she opened the floor, and every question was about the system. Why had the pre-op order set not been updated after the merge? Who was responsible for checking that, and did they know they were? When had the lab stopped phoning critical results, and had anyone assessed what was lost when it did? Should the night registrar have had any way to know that her pager being quiet was abnormal? Nobody asked who had made a mistake. When a junior doctor started to say that Ward 4B should perhaps have checked the bloods at midnight, the chair stopped her gently.

"We can talk about what the ward could have done differently," she said. "We don't talk about what the ward should have done. Should is for afterwards. What we want to know is what made it easy to miss."

Maya wrote that down.

On the way out, she passed a laminated poster by the door. It showed a simple diagram of stacked slices of Swiss cheese, holes lined up, an arrow passing straight through. *Every incident has many causes. Find them all.* Someone had stuck it to the wall with Blu Tack long enough ago that the corners had yellowed.

She thought about it all the way back to King's Cross. The hospital already knew how to do this, and had known for decades. Two miles away and a world apart, the people who wrote the software the hospital depended on had never been in the room.

---

Callum Dyer was thirty-one, friendly and unhurried, with an Arsenal mug and a standing desk he didn't use. He'd been at Meridian four years and was, by every account, one of the best engineers in Clinical Platform. He was not, Maya noted, defensive. He seemed genuinely interested in the question.

"Four minutes," he said, when Marcus put it to him. "Yeah. I've seen the timestamps. I'm not going to pretend it was longer."

"Talk us through them."

"Sure." He pulled the PR up. "I opened it. Read the description. It's a cleanup PR, removing dead code from Escalation's patient-matching, on a modernisation ticket I knew about. Checked the tests were green. Checked the dependency diff, which showed nothing added and nothing new pulled in. Skimmed the diff itself, which is mostly red, mostly removals. Checked nothing weird had been added among the deletions, like a new network call or a credential, the kind of thing that would actually worry me. Saw Sam had written it, and Sam's careful. Approved." He shrugged. "That's a normal review. That's what review is now."

"What would an abnormal review look like?"

"Reading it line by line." Callum said it without irony. "Which nobody does, honestly. Not for something like this. I get thirty, forty review requests a day. If I read every line of every PR, nothing would ship, and I'd be the bottleneck for the whole team. It's not realistic. The code's mostly written by agents now, and the agents are good. Better than most people at the stuff review used to catch. Typos, off-by-ones, null checks. So review has moved up a level. You kick the tyres. Are the tests passing? Has anything scary been added? Does the description make sense? Does it smell right?"

"And did this smell right?"

"Yes. It was a removal." Callum looked at the long red column on the screen. "Removals are the safest thing there is. You're making the system smaller. If you'd asked me before Monday what the lowest-risk kind of PR is, I'd have said dead-code removal with green tests."

"Who owns this code now?" Marcus asked. "After you approved it."

Callum frowned. "Sam, I suppose. It's his PR."

"Did Sam write it?"

"Well. The agent wrote it. Sam directed it."

"Did you read it?"

"I skimmed it."

"So who owns it? Who's the person who knows what it does?"

Callum opened his mouth, closed it, and after a moment laughed, not quite comfortably.

"That's a horrible question," he said. "I don't know. I've thought about that, actually. Not about this PR, just generally. When I started, if I'd approved your code, I'd have read it, so I'd have been half-responsible for it. I'd have known it. Now I approve maybe two hundred PRs a week and I couldn't tell you what most of them do in any detail. I trust the tests. I trust the author. I trust the agent, I suppose." He spun the Arsenal mug slowly on the desk. "I'm not sure anybody owns code anymore, in the way you mean. I think it just sort of exists."

---

The second thing Maya found that morning, she found by accident.

She was going back through the history of Escalation's patient-matching module in the code repository. She wasn't looking for anything in particular, just following Marcus's instruction to look at things and write down what she saw. She noticed a closed pull request from nine months earlier. It hadn't touched any code at all. It changed a single configuration file, the one that told the review tool who had to approve changes to which parts of the system.

The PR added one line.

```
/escalation/patient-matching/**   @rokafor
```

Its author was Ruth Okafor. The description was four sentences long.

*This adds me as a mandatory reviewer for changes to Escalation patient-matching, per R-117. This module contains safety-critical legacy behaviour that is not documented (see register). Until it is, I'd like to see any change to it before it merges. I'm happy to commit to a same-day turnaround.*

There was one comment, from Josh Whitfield, and then the PR had been closed.

*Thanks Ruth — appreciate the thought. I don't want to add a single-person bottleneck on a module we're actively modernising, and coverage is good. Let's revisit if we see actual issues.*

Maya read it several times. Then she went to find Marcus, who was standing by the coffee machine reading the same thing on his phone, because she'd sent it to him the moment she found it.

"*Let's revisit if we see actual issues*," she said.

"Yes."

"She offered to do it the same day. It wasn't even slow."

"Being slow had nothing to do with it." Marcus put the phone away. "Go and look at her review history. Not just this module. Everything."

She did. Ruth's reviews over the past year were the opposite of Callum's in every way. There were far fewer of them, perhaps a tenth as many. Each one was long and specific and full of questions. *What happens here if the lab sends a result with no units? Has this been tested with a result that arrives before the order is registered?* Some of her comments led to fixes, and some to long threads in which engineers explained, politely and at length, why the case she'd raised would never happen. A handful of the threads ended with somebody else on the team approving the PR over the top of her open questions, to get it merged. Next to some of her comments, someone had added a small emoji of a snail.

"There's a joke," Callum said, when Maya asked him about it, looking embarrassed for the first time that morning. "It's not a nice joke. People called it the Ruth tax. If Ruth was on your review, you'd add a day. It wasn't malicious. It was just that everybody else was approving in minutes, and she wasn't, so she stood out." He hesitated. "She was usually right, to be fair. About the edge cases. But usually the edge cases didn't happen."

"Until they did," Maya said.

Callum didn't say anything.

---

Marcus spoke to Ruth after lunch, at her desk under the window. Maya came with him and stood slightly back. She was conscious, without being able to say why, that this was a conversation Marcus had been waiting for since Monday morning.

He didn't introduce himself with any ceremony. He sat in the chair beside her desk and said, "I'm Marcus. I've read R-117, your steering paper, your notebook entry from two years ago, and your code-owners PR. I've read your reviews for the last year. You were right about all of it. I'm not here to make you tell me again."

Ruth looked at him for a long, level moment.

"Then why are you here?"

"Because I've found something you didn't know, and I thought you should hear it from me before it's in a report." He told her about the economy tier: the Q2 directive, the smaller context window, and the run log that showed the agent had loaded fourteen Java files and not `handlers.yaml`. Then he told her about the three merged records since January, and the man in Reading, readmitted with a bleed.

Ruth listened without moving. When he finished, she sat very still for some time.

"I didn't know about the context window," she said. "I should have thought of it."

"Why should you?"

"Because it's exactly the kind of thing that happens." She looked down at her notebook, closed on the desk. "You change something cheap and invisible at the bottom of the stack, it's fine ninety-nine times in a hundred, and the hundredth time it takes out a safety property somebody else was depending on without knowing they were. That's half of what I did in devices. You test the change against the hazard, not against the feature." She shook her head. "Nobody here thinks in hazards. They think in features. I've stopped expecting them to."

"Can I ask you something about review?"

"Of course."

"Callum thinks removals are the safest kind of change."

Something that was almost a laugh escaped Ruth.

"Removals of code you understand are safe," she said. "Removals of code you don't understand are the most dangerous thing you can do in a legacy system. That code's still there for a reason. Somebody, at some point, was bitten by something, and that's the scar." She put her hand flat on the notebook. "Do you know what I think the real change is, Mr Kwan? It isn't the agents writing code. It's that nobody's lazy any more."

"Go on."

"When I started, nobody would have rewritten two thousand lines of a ten-year-old module on a Monday afternoon. It wasn't that they couldn't. They couldn't be bothered. It was boring, it was risky, and it was a huge amount of effort for no new feature. So legacy code got left alone unless there was a very good reason, and when people did touch it, they touched the smallest amount they could get away with, because effort cost them something. That laziness was a safety feature. Nobody ever designed it. It just came for free with being human." She looked across the floor at the long rows of screens. "Now effort costs nothing. An agent will happily rewrite two thousand lines, and do it well, and the person asking doesn't feel any of the cost. So things get touched that would never have been touched. And the only thing that used to protect those scars was that people were too tired to go near them."

Marcus said nothing for a moment.

"I'd like to write that down," he said.

"You can if you like. I already have." Ruth opened the notebook to a page near the back and turned it towards him. In the same small even hand, dated eight months ago: *Laziness was a control. Nobody noticed when it was removed.*

Marcus looked at the line. Then he looked at Ruth, for a long moment, with an expression Maya hadn't seen on his face before. She thought it might be grief.

"Ms Okafor," he said, "would you be willing to help us? Not as a witness. As part of the investigation."

Ruth was quiet.

"What would that mean?"

"It would mean that when we stand up in front of the board, you're in the room."

"They'll say I'm biased."

"You are biased," Marcus said. "You've been right for eleven months. That's a very good bias to have."

For the first time since Maya had met her, Ruth Okafor smiled.
