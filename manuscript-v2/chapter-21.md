# Chapter 21 — Escalation, Again

They rebuilt Escalation first.

The regulator had given Meridian ninety days to show that the risk of recurrence had been addressed, "with evidence, not assurances", in a letter that Kalu had read aloud to Maya over the phone with something like admiration. Ashworth had retained Kestrel for the duration to monitor the pilot and report independently to the board. So Maya came to King's Cross two days a week through March and April, sat in a corner of the floor near the canal and watched the four of them work.

On the first day the four of them didn't work at all, or not visibly. Josh Whitfield, Ruth Okafor and Sam Ilyas sat around a table in Fleming with Helen Marsh. Helen had been seconded two days a week from Ward 4B, and she looked at the whiteboard, the lanyards and the barista downstairs with the polite suspicion of a person who'd spent nineteen years doing an actual job.

"I want to be honest," Helen said, about ten minutes in. "I don't know what an API is. I've never seen code. I don't know why I'm here."

"You're here because you were eight seconds from Mr Hale's bed," Ruth said, "and none of us were within eight miles."

Helen looked at her for a moment and then nodded slowly.

"All right," she said. "What do you want to know?"

---

It didn't go smoothly. Maya had expected that, but the shape of the friction surprised her.

For the first week Josh kept trying to measure things. He built a dashboard on the second day, from habit, with throughput, cycle time and lines changed, and put it on the screen in Fleming. On the third day Ruth asked him politely what any of it told them about whether a critical result would reach a doctor. He didn't have an answer, and he took it down. Then, in the second week, he swung too far the other way. He started second-guessing every agent session, and asked Sam to justify each prompt before running it. By Wednesday nothing had shipped. Sam was hedging every sentence again, *I think, maybe, sorry*, the way he had on the first Thursday in Fleming.

It was Ruth who sorted it out. Maya watched her do it, in a short conversation at the whiteboard that Josh would later describe to her as the most useful ten minutes of his career.

"Josh, stop," Ruth said. "You've got it backwards. This isn't a slow team. Most of what we're doing is ordinary work, and it should go at full speed. The new acknowledgement-tracking screen, the logging, the API for the ward dashboard, the migration scripts, the tests. None of that can hurt anybody if it's a bit wrong, and we'll see if it's wrong within the hour. Give it to the agents. Let them go. Review it the way Callum reviews things. Kick the tyres and merge it. I'm not here to slow that down. I'd be annoyed if you did." She drew a box on the whiteboard, a small one, in the corner. "This is the bit that matters. Patient identity. Merged records, retired references, anything that decides which human being a result belongs to. That's where somebody dies if we're wrong, and where we won't find out for six weeks. That's the only place we slow down, and we slow right down there, on purpose. Everything else goes as fast as the tools can go." She capped the pen. "Rigour isn't slowness everywhere. It's knowing where."

Josh stared at the small box.

"That's about five percent of the work," he said.

"Yes," said Ruth. "That's usually how it is."

After that it moved. In the first fortnight they shipped thirty-one changes to the parts of Escalation outside the box, most of them written by agents and reviewed in minutes. Maya counted, because Josh, from habit, still counted, and it was a good number to know. Inside the box they shipped nothing for three weeks.

---

What they did inside the box, for those three weeks, was mostly Sam's.

He didn't stop using the agent. Maya noticed that early and was relieved, because she'd half feared the lesson Sam would take from the last two months would be *do it all by hand*. The agent still wrote nearly all the code. But the shape of his work had changed completely, and it took her a while to see how.

In the first week he spent two nights on Ward 4B with Helen. He didn't write code. He sat at the nurses' station from eight in the evening to eight in the morning and watched what happened when results came in, when pagers went off, when they didn't and when a nurse went looking. He learned what a pre-op order set was and why it might still be carrying an old record three weeks after a merge. He learned how a registrar decides whether a potassium of six point one is a phone call or a walk down the corridor. He learned what Helen did when the ward computer was slow, which was to stop trusting it and go and look at the patient.

He came back to Fleming after the second night grey with tiredness and talking very fast.

"We've been thinking about it from the wrong end," he said. "Everyone has. Escalation, the old code, my PR, all of it. We start with the result and ask how to find the patient. But Helen doesn't start with the result. She starts with the patient. She doesn't care what number's on the sample. She cares who's in bed eleven." He went to the whiteboard and drew it, quickly and badly: a bed, a person, a stack of record numbers pointing at them. "Every record that's ever been merged into the live one has to resolve to this person, every time, forever. And if Escalation can't work out who someone is, it doesn't send it to an inbox and say *delivered*. It treats it as an emergency in itself. Not knowing who a critical result belongs to is a critical result."

Ruth studied the drawing.

"Yes," she said. "Write that down. That's the hazard statement."

He wrote it down. Then he spent two days with Ruth writing every way he could think of that a result might reach Escalation without a clean path to a person. Old records, merged records, records merged twice, records unmerged after a mistake, samples registered before the patient was, babies whose records were created before they had names. Helen added cases from the ward that neither of them had thought of: twins, a patient transferred between Meridian hospitals mid-admission, a woman who'd changed her name after a divorce. Ruth turned each one into a test. Then, and only then, Sam asked the agent to write the code.

It took the agent about forty minutes.

"That's mad, isn't it," Sam said to Maya that afternoon, watching the tests go green one by one. "Three weeks and forty minutes."

"Does it bother you?"

He thought about it. She noticed he took the time to think about it now, instead of apologising first.

"No," he said. "That's the weird thing. A month ago it would have. I'd have thought, the agent did the real work and I did the boring bit. But it's the other way round. The forty minutes is the boring bit. The three weeks were—" He stopped, and she saw him look for the word. "Do you remember on the towpath, Marcus asked what I'd feel when I fixed the audio in the emulator? And I said it was the working out. Deciding what's actually wrong, and what to do about it, and knowing why."

"I remember."

"That's what this was. That's all this was. Three weeks of working out what was actually going on and deciding what mattered. Except at the end of it, instead of Tetris making a noise, there's someone like Mr Hale in bed eleven, and the pager goes off." He laughed, a little self-consciously. "I thought the part of the job I'd lost was making things. It wasn't. I'd lost the bit where you decide what the thing's for and who it's for, and nobody had asked me to do that before. I didn't even know it was a job. It's the best bit. It's better than the typing ever was."

He turned back to the screen. The last test went green.

---

Josh delayed the release.

It was ready on a Thursday, nearly four weeks into the pilot. Every test was green, including Ruth's hazard tests and Helen's ward cases, and the agent had produced a clean, well-documented change. On the old team it would have gone out that afternoon. Josh looked at it at four o'clock, then looked across the table at Sam and Helen.

"Can you two trace every case by hand first?" he said. "Not the code. The cases. Walk through each one on paper, with a real patient journey, and tell me where the result goes. I don't want to know the tests pass. I want to know you two know."

"That's another week," Sam said.

"Yes."

"The regulator's ninety days—"

"Will survive a week." Josh glanced at Maya, who was in the corner and trying not to look as though she were watching. "A month ago, I'd have shipped it tonight. I'd have been right ninety-nine times out of a hundred, and that's what I used to be good at." He looked back at the screen. "I want to know we understand this one. Not because the agent might be wrong. It probably isn't. I want to know because in a year somebody's going to change it, and I want there to be two people on this team who know why every line is there. Everything else can go tonight. This waits."

Ruth didn't say anything. But Maya saw her write something in the black notebook, one line, and underline it.

---

Helen found it on the Tuesday of the following week, during the hand-tracing.

They were walking through the case of a patient merged twice, an old clinic record folded into a newer one which was later folded into a third. Helen frowned at the whiteboard.

"Hang on," she said. "This is just results, isn't it? Lab results."

"Yes," said Sam.

"What about alerts? When you merge records, do the allergy alerts come across? And the anticoagulant flags, the do-not-resuscitate orders, all the red banners we get at the top of the screen?"

There was a short silence in Fleming.

"That's not Escalation," Josh said. "That's—" He stopped.

"That's one of the four," Ruth said quietly.

Tariq came over from behind his fern within ten minutes. They put his graph up on the screen and found the node: the clinical-alerts service, one of the four on his list of eleven that, as far as he could tell, didn't handle merged records at all. The clinical safety team had put it on their list of things to review in the first week after the board. They hadn't reached it yet. It hadn't failed in any way that anyone had noticed. It wouldn't have, because an alert that's missing doesn't raise an error. It just isn't there.

Sam wrote the query and Ruth checked it. Helen read the results out, one at a time, in the flat clinical voice Maya remembered from the incident statements.

There were four. Four patients currently admitted across Meridian's hospitals had a safety alert sitting on a retired record that didn't appear on their live one. Two were penicillin allergies, one was an anticoagulant flag, and one was a documented history of malignant hyperthermia under anaesthesia.

That one was at Meridian Reading. According to the theatre list, she was due for a knee replacement under general anaesthetic at eight the next morning.

Helen was on the phone to the Reading duty anaesthetist before Sam had finished reading the screen. Maya watched her through the glass wall of Fleming, standing with one hand flat on the desk, speaking quickly and calmly in the voice they trained you to use. Josh had gone very pale. Ruth sat entirely still with her notebook closed in front of her.

The anaesthetist rang back at ten past six. They had found the old record, confirmed the history with the patient's GP and changed the anaesthetic plan. The surgery would go ahead the next morning, safely.

Nobody in Fleming said anything for a long time after Helen put the phone down.

"The old way," Sam said eventually, very quietly. "If we'd shipped on Thursday. We wouldn't have been tracing cases. We'd never have—"

"No," said Josh. "We wouldn't."

He looked at Helen, who had sat down and was staring at her hands.

"How did you think of it?" he asked.

Helen looked up at him.

"Because I'm the one who reads the red banners," she said simply. "Every day. You don't. You've never seen one."

---

Maya wrote it into her interim report to the board that night, in plain language, without adjectives. She described a four-person team, a five-percent box, three weeks and forty minutes, a delayed release, a nurse who read the red banners, and four patients. One of them was in theatre at eight the next morning, with a different anaesthetic.

She sent a copy to Marcus, unsummarised.

He replied twenty minutes later, with one line.

*That's evidence, not assurance. Well done. Tell Helen.*
