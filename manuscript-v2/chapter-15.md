# Chapter 15 — Six Days

In the taxi to Paddington, Tariq sat with his laptop clutched on his knees as if it might escape. Maya read the last document Kalu had sent her that morning, the one she'd asked for on Wednesday and half hoped wouldn't arrive.

It was Ruth Okafor's most recent annual performance review.

It was a standard Meridian form, rated on five dimensions. On *Technical excellence* Ruth was rated *Exceptional*. On *Quality and safety*, *Exceptional*. On *Delivery*, *Below expectations*. On *Collaboration and pace*, *Below expectations*. On *Embracing new ways of working*, *Needs improvement*.

Below that, in the comments box, Josh had written: *Ruth is one of the strongest engineers I've worked with technically and her attention to detail is second to none. However, her approach to review and risk has at times created friction and slowed delivery for the team, and she has been reluctant to adopt the AI-first practices that are central to our engineering strategy. I'd like to see Ruth find ways to apply her expertise without becoming a bottleneck.* A second comment followed, from the calibration panel Felix had chaired. *Rating moderated down from Meets to Below on Collaboration to align with peer group. Recommend development move to test tooling to make best use of strengths.*

The overall rating was *Partially meets*. A note at the bottom recorded that she was therefore ineligible for that year's bonus.

The review had been completed four months after the date on R-117, and two months after her steering paper.

Maya read it twice and then closed the laptop and looked out of the window at the wet traffic on the Euston Road. It was what she'd expected. She'd known since Thursday what she was going to find, and it still went into her like a splinter. Ruth had written it down. She'd done everything the organisation asked of someone who saw a risk. In return the organisation had put in writing, on her permanent record, that she was the problem, then cut her pay and moved her off the service she'd warned about, three weeks later. Meanwhile it was paying four thousand pounds a month for one of her colleagues to run agents overnight.

None of it was secret, and none of it was even unusual. The organisation hadn't punished her for being right. It had simply measured her by things she had chosen not to be good at, because she thought they were dangerous, and then believed its own measurements.

"Are you okay?" Tariq said.

"Yes." Maya put her glasses back on. "Tariq, when we get there, I'm going to ask you to show them the graph. Just the graph, and the eleven nodes, and the benchmark result in one sentence. Don't explain. They won't follow it and you'll lose them. Just show it and say what it is."

He looked as though she'd asked him to jump out of the taxi.

"Okay," he said.

---

They were shown straight up to the twelfth floor and along the corridor to Ashworth's office. The door was ajar. Maya heard Felix's voice before she saw him. It was warm and fluent, the voice he'd used to show her the map of glowing conversations.

"—a clear, proportionate response, which is what the regulator wants to see. We've identified the change. We've identified the engineer. I think we accept that there was an individual failure of judgement, compounded by a review lapse. The engineer concerned exits the business with appropriate support, we bring in a senior architect to oversee Clinical Platform's legacy estate, and we commission an independent review of AI tooling governance. That gives us something concrete to say this afternoon. It also protects the wider programme, which frankly is doing extraordinary things for patients and shouldn't be—"

Maya knocked once and walked in.

Ashworth was behind her desk. Kalu was in an armchair by the window with his legal pad. Felix stood by a wall-mounted screen showing a slide titled *Proposed response: Kingsgate SI*. He turned as she came in and his face went through surprise, irritation and charm in under a second.

"Maya. Great. You're early. We were just—"

"I heard," Maya said. "I'm sorry to interrupt. I'd like a chance to respond before anyone decides anything."

Ashworth looked at her steadily. "Felix was outlining options. Nothing's been decided."

"Then I'd like to add some."

"Deborah," Felix said, still smiling, "with respect, Maya's been here a week and a half. We've got a story in the *Guardian* that names the Assistant, and a regulator who—"

"The engineer you're proposing should exit," Maya said, "is twenty-four. He used the tooling the way Meridian told him to, with a Skill from Meridian's own internal library, on a model tier Meridian moved him to in order to cut costs. His change was approved by a senior engineer in four minutes, which is the standard Meridian review practice. It removed a method that one of your own engineers had warned you about, in writing, eleven months ago, in your own risk register." She put her laptop on the edge of Ashworth's desk and opened it. "That warning was downgraded. A plain-English version of it was put in front of Felix's steering group and summarised by your AI tooling into a green bullet point saying *no committee action required*. The engineer who wrote it was rated below expectations a few months later, lost her bonus, and was moved off the service. Her name is Ruth Okafor. She's the reason I know what `normaliseRef` is."

There was a silence in the room. Felix had stopped smiling.

"That's not—" he began.

"I'm not saying it to blame you," Maya said, and found to her surprise that she meant it. "I don't think you knew. I don't think anyone above Ruth knew, in a way that meant anything. That's my point." She turned to Ashworth. "If you exit Sam this afternoon, you'll be telling the regulator it was one person. In six months, or a year, you'll be back here with a different patient and a different twenty-four-year-old, and I'll have to tell you about this conversation."

Ashworth's face didn't change. "Go on."

"Tariq." Maya stepped back. "Show them, please."

---

Tariq stood up as if from very far away. He plugged his laptop into the screen beside Felix's slide, his hands not quite steady. The sprawling grey graph filled the wall. He typed his query and the eleven orange nodes came up out of the grey.

"These are all the places in Meridian that work out who a patient is," he said. His voice was quiet but it didn't shake. "There's supposed to be one. There are eleven. Four of them don't handle merged records, and I don't know yet whether that matters. Nobody owns all of them." He swallowed. "And this morning we tested the Skill that made the change against the original version. On twelve cases where code looked dead but wasn't, the original stopped and asked about nine. The current version removed eleven."

He stopped. Then, as if remembering Maya's instructions, he unplugged the laptop and sat down.

Ashworth was still looking at the wall where the graph had been.

"Four of them," she said.

"Clinical safety have the list as of Wednesday," Maya said. "They're reviewing them. We also found two other patients since January whose critical results went to fallback because of the same change. Both were missed for hours. One was readmitted with a bleed. Nobody connected them, because the system reported them as delivered."

"I wasn't told that," Felix said. He said it quietly, almost to himself.

"No," Kalu said from the armchair, without looking up from his pad. "You weren't. Nobody was. That's rather the point she's making, Felix."

"Thank you, Bob," said Ashworth drily.

---

Ashworth stood, walked to the window and stood looking out at the rain over Paddington Basin. When she turned back, her voice had returned to the smooth register of a statement prepared for camera. Maya had already learned that this was how she sounded when she was thinking hardest.

"Here is my difficulty, Ms Reyes," she said. "At one o'clock today the regulator rang me. They've seen the *Guardian*. They want preliminary findings before our board meets, not after, and they want to know what we're doing about the risk of recurrence. I've brought the board forward. It now meets next Thursday." She paused. "You have six days, not seven."

Maya felt the number land.

"The board," Ashworth went on, "will not be satisfied with *it's complicated*. Neither will the regulator. Neither, frankly, will I. Felix's proposal is clear, it's actionable and it's defensible. Yours, as far as I can tell, is that the entire way we build software is faulty, that nobody in particular is responsible, and that I should explain this to a journalist who thinks our chatbot nearly killed a pensioner." She held Maya's eyes. "You may well be right. But being right is not the same thing as being useful."

"I know."

"Do you?" Ashworth came back to her desk. "Because I've hired people before who were very right and of no use to me whatsoever. They wrote me forty pages about root causes and left me to work out what to do on Monday." She sat down. "I won't exit anybody today. I'm not going to make Felix's statement this afternoon. We'll say we're investigating thoroughly and independently, which is true, and that the Assistant was not involved, which is also true and which I intend to say very loudly. But on Thursday, Ms Reyes, you'll stand in front of my board, and you'll bring me something I can act on. Not a diagnosis. A plan. If you can't, I will do what Felix suggests, because at least it's something, and I won't be able to defend doing nothing."

"Understood."

"Good." Ashworth turned to Felix. "Felix, I'd like the full list of the eleven services on my desk by Monday, with an owner for each one. Not a team. A person."

Felix looked at her, then at the blank screen, and then, briefly, at Maya. She couldn't read what was in it. It might have been resentment, or the beginning of something worse for him than that: the realisation that he had been confidently describing a building he'd never been inside.

"Of course," he said.

---

In the lift going down, Tariq leaned against the mirrored wall and closed his eyes.

"Was that okay?"

"That was perfect."

"I nearly threw up."

"So did I," said Maya, and he laughed, and she found that she had laughed too.

Out on the pavement, in the rain, she rang Ruth. She wasn't sure why. It wasn't to share good news, because there wasn't any yet. Ruth answered on the second ring.

"I read your performance review," Maya said. "I'm sorry. I should have asked first."

There was a long pause on the line.

"It's fine," Ruth said. "It's a document. People should read documents." Another pause. "What did you think?"

"I thought you were right about everything, and you were punished for it, in writing, by a process that thought it was being fair." Maya stood under the awning of a coffee shop and watched the buses go by. "I said that to the chief executive this afternoon, more or less."

The silence on the line went on so long that Maya thought the call had dropped.

"Thank you," Ruth said at last. Her voice was very even, the way it always was. "Temi's going to ask me tonight how my day was. I usually say *fine*." A small pause. "I think I'll tell her the truth."

---

Marcus was waiting for them back at King's Cross, in the corner, with the thermos and two cups.

"Six days," Maya said, sitting down.

"So I heard. Kalu texted me." He poured the tea. "How was Felix?"

"He was trying to fire Sam when I walked in."

"Of course he was. It was the only lever he could see." Marcus handed her a cup. "Don't hate him for it. He's not a bad man. He's a man who's been told to steer a ship from a room with no windows, using a dashboard that only measures speed. When it hit something, he reached for the one control he understood." He sat back. "Kalu says the chair's calling an emergency session of the full board on Monday. They'll want a name. Not Felix, not Ashworth. The non-executives. They'll want it more than either of those two, because they're further from it."

"How do you know?"

Marcus smiled faintly.

"Because I've sat on one," he said.
