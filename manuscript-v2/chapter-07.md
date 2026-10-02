# Chapter 7 — How Do You Know That?

"You sound tired," Lucia said on Sunday.

"I'm fine."

"You always say *I'm fine* in that voice when you've found something you don't like." Her sister was in her garden in Bristol. Maya could hear the children arguing over a football, and a wood pigeon. "Is it the hospital thing? The chatbot?"

"It wasn't the chatbot."

"The paper said—"

"The paper was wrong." Maya was lying on her sofa with her glasses on her chest, looking at the ceiling. "It was a very boring piece of software nobody's ever heard of, and a very boring decision about it that nobody remembers making."

"That sounds worse."

"It is worse," Maya said, and was surprised to hear herself say it.

---

Marcus Kwan arrived at King's Cross at eight on Monday morning, which was an hour before anyone in Clinical Platform did, in a waxed jacket so old it had gone pale at the seams and a grey cardigan underneath it. He carried a canvas bag holding, as far as Maya could tell, a notebook, a thermos and an apple. He was sixty-eight and looked it, and seemed entirely unbothered about that. When she'd first worked with him, she had been struck by how little he said in meetings and how completely the meetings rearranged themselves around him anyway.

"Eleven days," he said, by way of hello.

"Eleven days."

"Then let's not waste the first one agreeing with each other." He sat down at the desk they'd been given, a hot-desk in a corner of the Clinical Platform floor with a view of the canal, and took out the notebook. It was full. He had clearly spent the weekend in it. "Tell me what caused this."

"PR four-four-seven-one removed `normaliseRef`. Without it, results against merged records couldn't find an admission and went to the fallback inbox."

"That's what happened. I asked what caused it."

She'd known he would say something like that. She still felt a flicker of irritation.

"Sam removed it because it looked dead, and it looked dead because it was wired in through config. Nobody documented it, and the risk Ruth raised was downgraded. The review didn't catch it."

"So the cause is Sam."

"No. That's not what I—"

"You listed Sam first." He looked at her mildly. "You'll do that in the report too, if you're not careful. The first thing in a list is the cause, as far as any reader's concerned, and the rest is context. Why is Sam first?"

"Because his change is the one that broke it."

"Is it?" Marcus turned a page. "The code that was removed in January was written in 2017 to patch a near-miss nobody wrote up. That's Ruth's note. In 2019 the lab stopped phoning critical results to wards, because Escalation was more reliable than a phone call. That's in your timeline, which I read three times. So, from 2019 onwards, a single undocumented thirty-line method was the only thing between a merged record and a missed critical result. There used to be two safety nets, the code and the phone. Somebody decided in 2019 that you only needed one, and that it was safe to rely on a piece of code nobody understood. I'd like to know who decided that, and whether they knew the method existed." He put the notebook down. "If you're going to name a moment, why not that one?"

Maya was quiet for a second.

"I didn't know about the phone calls," she said. "I mean I knew, it's in the timeline. I didn't connect it."

"No. Because you started from the PR and went backwards, and the PR is very loud." He said it without any judgement in his voice. "Everybody starts from the loudest thing. It's the most recent and the most visible, and there's a named person attached to it. That isn't analysis. It's whatever happened last."

"So what do you start from?"

"I don't start from anything. I ask people how they know what they think they know, and I keep asking until somebody has to go and check." He stood up. "Who's the team lead? Whitfield?"

"Josh."

"Let's go and ruin his morning."

---

Josh was at his desk by nine, and Marcus was standing beside it at one minute past. Maya watched Josh register the cardigan, the bag and the stillness, and visibly decide that this man was more dangerous than he looked.

"Josh, I'm Marcus. I'm helping Maya. I've got a few questions, and they're going to sound stupid. Please answer them anyway."

"Sure. Of course."

"Is Escalation the only service that relies on the merge chain?"

Josh hesitated. "I think so. It's the only one that would need to. Most services just use the MPI's own lookup."

"How do you know?"

"Well—" Josh stopped. "I'm not actually sure we've checked. I'd assume—"

"Could someone check?"

"I— yes. Yeah. Tariq would know, probably. He knows the dependencies better than anyone." Josh wrote something down. "I'll ask him."

"Thank you. Second stupid question. Mr Hale's was the first critical result to go wrong since the January change?"

"Yes. It's the only incident."

"How do you know?"

Josh opened his mouth, then closed it. Maya saw the question land and the colour leave his face.

"Because nobody's reported another one," he said.

"That isn't the same thing," Marcus said gently. "Mr Hale's was found because he arrested on a ward at quarter to six in the morning. If he'd been less unlucky, or if a nurse had happened to check his bloods at midnight, nobody would know about his either. How many critical results have gone to the fallback inbox since the twelfth of January?"

"I'd have to query it."

"Could you query it now?"

Josh looked at Maya as if she might rescue him. She didn't. After a moment he pulled his keyboard towards him and started typing.

It took him twelve minutes. Maya timed it on her phone, partly out of habit and partly because she couldn't think of anything else useful to do with her hands. Marcus stood beside the desk the whole time without speaking, watching the screen. Every so often he took a bite of his apple.

When the query came back, Josh sat very still.

"Fourteen," he said.

"Fourteen critical results to fallback since the twelfth of January?"

"Yes." Josh scrolled. "Most of them are fine. They're outpatients. People who had bloods taken at a clinic and went home. They don't have an admission, so the result's supposed to go to the clinic inbox, that's correct behaviour. That's what the fallback is for." He kept scrolling. His voice dropped. "Three of them are merged records."

"Three."

"Mr Hale. And two others." Josh clicked into them. "A woman at Kingsgate in January. Critical sodium. It went to an outpatient inbox in Harrow, but she had a repeat blood test on the morning ward round, and the ward picked it up from that. Four hours late." He clicked again. "And a man at our hospital in Reading, two weeks ago. Critical haemoglobin. He was discharged before anyone saw it. The result went to his GP's inbox on the Monday. He was readmitted on the Wednesday with a bleed." Josh's hand had stopped moving on the mouse. "Nobody connected it. It went through as a normal readmission."

There was a long silence in the corner of the floor.

"Before January," Marcus said quietly, "in a typical six weeks, how many results against merged records would go to fallback?"

Josh ran it. "None. Zero. Because `normaliseRef` caught them all."

"So the rate went from zero to three in six weeks, and there was nothing watching the rate?"

"We monitor errors. Exceptions, failures, latency." Josh's voice was barely audible. "Fallback isn't an error. It's a valid outcome. It says *delivered*."

Marcus nodded slowly, as though he'd expected exactly that and taken no pleasure in being right.

"Thank you, Josh," he said. "That was a very good query. I'd like you to send it to the clinical safety team now, please, with the two patient numbers, before you do anything else this morning. They'll want to look at both of them properly. And I'd like you to set up an alert, today, on the rate of fallback routing for inpatient results. Not errors. Rates."

"Yes. Yes, of course." Josh was already moving. "God. Yes."

---

Back at their desk by the window, Maya sat down heavily.

"Three," she said.

"Three that we know about."

"I had that query in my head. Not the query, but the idea of it. I thought: was this the first one? And then I thought, well, it's the only incident, and I moved on."

"You moved on because the organisation told you it was the only incident, and the organisation sounded sure." Marcus unscrewed his thermos and poured something that smelled of green tea into the lid. "It always sounds sure. That's its job. Every organisation is a machine for producing confident statements about itself. Most of them are true. Your job is to find the ones that aren't, and you won't find them by listening to how confident they sound. You'll find them by asking how anyone knows."

"Is that the whole method?"

"It's most of it." He sipped. "The rest is noticing when you've stopped asking because you're tired, or because you like the answer, or because you've already written the report in your head." He glanced at her over the thermos lid. "You did write it in your head. On Thursday."

She didn't bother denying it. "Four minutes."

"I'd have guessed five. You're quicker than you were." He put the lid back on. "It's not a crime, Maya. Everybody does it. The good ones write it down and then set fire to it."

"I put it in a folder."

"Then set fire to the folder."

She laughed despite herself, and the laugh came out shakier than she wanted.

Across the floor, under the far window, Ruth Okafor had arrived. She hung her coat on the back of her chair, set her black notebook squarely beside her keyboard and sat down without looking towards anyone. Maya saw Marcus watch her do it. He watched for longer than she'd have expected, and with an expression she couldn't read.

"That's her," Maya said.

"I know."

"Do you want to talk to her?"

"Not yet." He turned back to his own notebook. "When I talk to her, I want to have something to say that she doesn't already know. She's been explaining this to people for eleven months. I'm not going to make her do it again for a man in a cardigan."

He wrote something, and Maya, reading upside down, made out two words, underlined twice.

*Protect her.*

Then he closed the notebook, picked up the bag and stood.

"I'm going to walk the floor," he said. "I want to watch how people work. Don't follow me. Tonight I'm taking you to dinner."

"Marcus, we've got eleven days."

"Ten and a half, now. You'll want to eat at some point." He was already putting on the waxed jacket. "Half seven. I'll send you the address. Don't be late. The chef doesn't hold the counter for anybody, including me."
