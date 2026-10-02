# Chapter 10 — Following the Money

"Every investigation I've ever done," Marcus said, "eventually turns out to be about money. Not always in the obvious way. But somebody, somewhere, made a decision because something cost less, or because something else would cost more, and nobody wrote down the trade."

"You sound like Kalu."

"Kalu's a lawyer. Lawyers know everything is about money. They're just too polite to say it before the invoice."

The finance business partner for Digital Services was a woman called Nadia Kerr. She had a corner desk on the third floor of the printworks, two monitors and a whiteboard covered in a dense tangle of arrows that she apologised for and didn't rub out. She had clearly been told to expect them and had prepared. Maya liked her within a minute.

"You want to know what we spend on AI tooling," Nadia said. "The honest answer is that I can tell you the total to the penny and almost nothing about what's inside it."

"Start with the total," Marcus said.

"Three point four million pounds a year, as of this financial year. That's the coding agents, model usage, the enterprise licences and the internal platform that sits on top. Two years ago it was a little over three hundred thousand. Eighteen months ago it was one point one million." She pulled up a chart. It was the same shape as Felix's adoption curve. "It's now the third-largest line in the Digital budget after salaries and cloud hosting. Last year it overtook the contractor budget."

"Who approved the increases?"

"Felix. The jump from one point one to three point four went through the Digital investment committee last spring. I've got the paper." She sent it to the screen.

It was six pages long and very well designed. Maya recognised the visual language from the dashboards on the second floor: clean charts, confident headings, a palette of Meridian teal. *AI-First Engineering: Scaling What Works.* The case was simple and, on its own terms, compelling. Pull requests merged per engineer were up two point three times. Cycle time was down forty-one percent. Feature delivery against roadmap was up. Engineer satisfaction with tooling stood at eighty-four percent. There was a quote from a team lead: *"I can't imagine going back."* At the bottom was a recommendation to triple the budget and remove per-engineer usage caps, *to let our best people go further*.

Maya read it twice, then a third time looking for something specific.

"There's no risk section," she said.

"No," said Nadia.

"Is that normal?"

"For an investment paper above a million pounds, no. The template has one." Nadia scrolled to the end, where a heading said *Risks and mitigations* and underneath it, in a single line: *Cost growth — mitigated by productivity gains.* "That's it. That's the risk section."

Marcus leaned forward and studied the charts.

"Every number in this paper measures how much was produced," he said. "Pull requests. Cycle time. Features. Satisfaction with the tools. There's no number here about what was produced. Nothing on defects, rework, incidents, or how often a change has to be reverted. Nothing on how long it takes a new engineer to understand a service." He sat back. "It's a paper about the speed of the conveyor belt. It doesn't say anything about what's on it."

"To be fair to Felix," Nadia said, "nobody had those numbers. We still don't, really. Nobody's ever asked me to work out what a defect costs." She hesitated. "And to be fair to Felix again, the velocity numbers were real. Things really did get faster. He wasn't making it up."

"I don't think he was making anything up," Marcus said. "I think he asked the only question he knew how to ask, and got a very good answer to it."

---

"Can you break the spend down by person?" Maya asked.

Nadia gave her a long look.

"I can," she said. "I was asked not to circulate it. It's quite sensitive."

"We're not going to circulate it."

Nadia hesitated, then opened a spreadsheet. "These are monthly averages over the last six months, per engineer, for Digital Services. Anonymised, except where I've been given permission. Sorted by spend."

Maya looked at the top of the column, then the bottom, then the top again, because she didn't believe it the first time.

The top row read *£4,180*. The bottom of the column, among a cluster of very low numbers, had one named row, the only named row on the sheet, and next to it *£15*.

"Ruth Okafor," Maya said.

"She asked me to put her name on it," said Nadia. "When I first ran this, last autumn. She said she wanted it on the record that her usage was low on purpose, not because she didn't know how." She tapped the screen. "Fifteen pounds a month, flat, six months running. She uses it to search documentation and draft emails. She doesn't use agents at all."

"And the top?"

"Anonymised. A Clinical Platform engineer." Nadia's face gave nothing away. "Four thousand one hundred and eighty pounds a month, on average. Runs agents most nights."

"That's two hundred and eighty to one," Maya said. "Between two engineers on the same team."

"Same team, same tools, same access. Nobody told either of them how much to use. That was the policy." Nadia scrolled. There were more than six hundred rows. The numbers ran from four figures, through a long fat middle of a few hundred pounds a month, down to a scatter of near-zeros at the bottom. "We call this the long tail at finance meetings. It's a joke, but not much of one. Some people are spending more on AI than we pay them in a week. Some people have basically never logged in. I can't tell you which group is doing better work. Nobody can. We've never measured it."

Marcus was looking at the spreadsheet with an expression Maya had seen him wear once before, years ago, at a client who'd shown him a beautifully laminated safety manual.

"Two people on the same team," he said quietly, "who disagree by a factor of two hundred and eighty about how much to trust a tool with patient safety. And nobody's ever put them in a room together."

---

"It's about to get worse," Nadia said. Then she hesitated. "I think. Honestly, I'm not sure how much worse."

She stood up, uncapped a pen, and looked at the tangle of arrows on her whiteboard as if hoping it would explain itself.

"Our main vendor is changing how they charge us from April. At the moment it's a big flat licence. From April it's going to be based on usage, how much each person actually uses it." She tapped an arrow. "That's the bit I can't model. Their account manager sent me a calculator, and depending on what I put into it, next year's bill is anything from roughly the same to double. I asked the engineering leads what our usage will look like next year, and they all said *more*, and none of them could tell me how much more." She tapped a second arrow. "And the price keeps moving anyway. Twice last autumn the bill jumped and nobody here had changed anything. The vendor had changed something at their end. One of the engineers tried to explain it to me. I wrote it down, and I still don't really understand it." She put the cap back on the pen. "What I keep trying to tell people is that I can't tell the board what this costs next year. I also can't tell them what happens if we cut it. If we halve the spend, do we lose half the speed? A tenth? None? Nobody knows, because nobody's ever been able to tell me what the spend actually buys."

"Have you said that to Felix?"

"I've said it in every quarterly review." Nadia sat down. "He says it's an investment, and the productivity numbers justify it. And then last year, in the middle of all that, I was told to get spend down."

"When?"

"Q2. After the first big spike, before the committee approved the new budget. There was a directive from Felix's office to cut AI spend thirty percent per engineer across Digital, as a holding measure." She pulled up an email. "Teams could decide how. From what I understand, a lot of them switched to a cheaper setting on the platform. The engineers call it *economy*. I don't really know what it changes. They told me it was fine for most things, and the bill did go down."

Marcus had gone very still.

"Which teams moved their defaults?"

Nadia checked. "Most of them. Clinical Platform did in June." She read from the email. "*All shared Skills moved to economy by default unless an engineer overrides.* Whatever that means in practice."

"And the Skill that was used in PR four-four-seven-one?"

"I wouldn't know that. That's an engineering question."

"Then we'll ask an engineer," Marcus said, standing up. "Thank you, Nadia. You've been extremely helpful. Can I ask you one more thing?"

"Of course."

"Has anyone else ever asked you for that spreadsheet?"

Nadia thought about it.

"Ruth did," she said. "Last autumn. When she asked me to put her name on it. She asked to see the whole distribution." She paused. "She said she wanted to know how worried to be."

---

It took Josh a few minutes to find the agent's run log for #4471. The platform kept a record of every session: which Skill was invoked, which model, which files the agent had loaded into its context, and how many tokens each step had used. Josh read it out in a voice that got quieter as he went.

"`legacy-simplify`. Model tier: economy. Context window: thirty-two thousand tokens. Files loaded…" He scrolled. "Fourteen. All the Java in the patient-matching package. The tests." He scrolled again, slowly. "Not `handlers.yaml`."

"Would it have loaded it on the standard tier?"

"I don't know. Maybe. The standard tier has eight times the context. The Skill tells it to look for config references, and on a bigger window it usually pulls in the whole config directory." Josh sat back. "On economy it has to choose. It chose the Java."

"So the agent never saw the one file that would have told it the method wasn't dead."

"It couldn't have. It didn't have room." He put his hands flat on the desk. "We moved to economy in June because we were told to get spend down, and nearly everything worked fine on it. It still does. I'd have made the same call again. I did make the call." He looked up at Maya. "That's on me, not Sam."

"It's not on you either," Marcus said. "Not on its own. You were told to save thirty percent, by people who'd been told the risk was *cost growth, mitigated by productivity gains*, and you found a way to save it that worked nearly all the time. That's what good engineers do. The trouble is that nobody, at any level, was in a position to ask what *nearly* was going to cost when it ran into a module like this one."

---

That evening, in the corner by the canal window, Maya laid it out on a single sheet of paper. It was still the same failure, but she could see more of it now.

The code had been undocumented since 2017. In 2019 the phone calls stopped and the second safety net went with them. R-117 was downgraded and the steering paper flattened into a green bullet. Throughout, usage had been allowed to drift two hundred and eighty to one, uncounted and undiscussed, as if it were a matter of personal taste. The budget had been tripled on the strength of a paper that measured only how fast things were made. A cost cut moved the Skill to a smaller window, so the agent couldn't see the one file it needed. A junior read every line carefully and wasn't scared of the right thing, in a place where not knowing was what the job felt like.

She didn't like what it added up to.

"It's getting bigger," she said.

"It always does at this stage." Marcus was packing his canvas bag. "Then it gets smaller again, once you understand it. You're not there yet." He paused. "Josh said Tariq knows the dependencies better than anyone."

"Josh said that yesterday."

"I know. He also said he'd ask Tariq whether anything else relies on the merge chain." Marcus put on the waxed jacket. "I checked this afternoon. He's asked, but he hasn't chased it, and Tariq hasn't come back to him. I don't think either of them forgot. I think they're both afraid of the answer." He picked up the bag. "Let's go and find out tomorrow what he's afraid of."
