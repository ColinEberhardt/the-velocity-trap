# Chapter 20 — Thursday

There were two chairs against the wall by the door of the large boardroom when Maya and Ruth arrived at ten to nine. Maya looked at them, then at the long table where the directors' name cards had been set out, and then at Pell's assistant, a young man with a clipboard.

"We'll need two places at the table, please," she said. "Ms Okafor is presenting."

The young man looked at his clipboard. "I'm afraid the seating plan—"

"I'm sure Mr Pell won't mind," said Kalu, coming in behind them with his legal pad under his arm. "I'll move up."

He moved his own name card two places along, and the young man, after a moment's visible distress, brought two more chairs. Ruth sat down at the table, upright, with her black notebook squarely in front of her. She'd worn a dark jacket Maya hadn't seen before. She looked entirely calm. Maya, who had slept for about two hours, envied her that.

The room filled. Today it was all in person: Pell at the head of the table, David Strand halfway down with his arms folded, a clinical non-executive, the chief financial officer, two other directors Maya didn't know, Ashworth and Felix side by side. Marcus had again not been invited. He was downstairs in the café, doing the crossword. He'd said that morning, "If I'm in the room, they'll think it's my finding. It isn't."

Pell opened the meeting and summarised the regulator's position: preliminary findings today, and any remediation to be evidenced, not asserted, within ninety days. Then he asked Maya to begin.

She stood up.

"I'd like to start with something one of your engineers wrote eleven months ago," she said. "I think she should present it herself."

---

Ruth didn't stand. She opened her notebook to a marked page, looked at it briefly, closed it again, and spoke.

"My name's Ruth Okafor. I'm a senior engineer in Clinical Platform. Before Meridian I spent fifteen years writing firmware for infusion pumps." Her voice was quiet and perfectly even, and the room went still to hear it. "In medical devices, before you change anything that could hurt a patient, you write down the hazard. Not the feature, the hazard. What could go wrong, how badly, how likely, and what you're going to do to stop it. Then you test the change against the hazard, and someone who didn't make the change signs it off. It's slow. It's also the reason pumps don't often kill people."

She told them about `normaliseRef`. She explained, in four sentences, what a merged patient record was and why a result could arrive against the wrong one, and what the thirty lines of code had done about it. She told them she'd found it two years ago and written it down. Then she read them R-117, all of it, word for word, from her notebook, including the line *Results will appear delivered.* She told them what had happened to it. She didn't tell them what had happened to her afterwards. Maya noticed that she left it out, deliberately, and noticed the clinical non-executive notice it too.

"I'm not here to say I was right," Ruth finished. "I was right about one module. There are two hundred services in Digital, and I've only looked properly at about six of them. I don't know what's in the others. Nobody does. That's what I'd like the board to be worried about."

She put her hands flat on the notebook and stopped talking.

There was a silence. It was the clinical non-executive, a retired cardiologist called Dr Fennimore, who broke it.

"Thank you, Ms Okafor," she said. "That's the clearest description of a clinical hazard I've heard from this organisation in four years." She turned to Felix. "Felix, had you seen that risk before this week?"

Felix opened his mouth, closed it, and said, "No. Not in that form."

"What form had you seen it in?"

"A slide," Felix said, after a moment. "It said minor."

---

Maya took them through the rest in twenty minutes. She'd cut it down three times in the night, and she spoke without slides, from one sheet of paper.

She told them about the phone calls that stopped in 2019, the Skill edited eight times without a test, the economy tier and the thirty-two-thousand-token window. She described the four-minute review, and Callum, who wasn't sure anyone owned code any more. She explained the three hundred and forty pages of documentation that had the warning in them, and the PR description that had it as item three of seven. She showed them Nadia's spend table and the two hundred and eighty to one, and the investment paper whose only risk was *cost growth, mitigated by productivity gains*. She put Tariq's graph up on the screen for exactly as long as it took to say *eleven*, and the benchmark for as long as it took to say *nine* and *eleven*. She told them about the three patients since January, and the two near-misses that had been logged as delivered.

She didn't use any of the sentences from her notebook, the three from Sam and Tariq and Josh. Those weren't hers to use in this room. But she said: "Every engineer I've spoken to in the last two weeks, from the most junior to the most senior, has told me in some form that they no longer feel they really understand the systems they're responsible for. They each thought it was just them. It isn't. It's the most consistent finding of this investigation."

Then she put the sheet down.

"Here's what happened," she said. "Meridian adopted extremely powerful tools that make it far faster to produce software. It did that without changing anything about how its teams are shaped, or how it decides what's safe, or how it knows whether things are working. So the tools did what they're good at: more, faster, and better-looking. Meanwhile the things that used to keep people near enough to notice a problem were removed one at a time, each for a good reason. Mr Hale was at one end of that. Ruth's warning was at the other." She paused. "This wasn't one person's mistake, and the cure isn't one person's removal. If it were, I'd tell you."

David unfolded his arms. "We've heard the diagnosis, Ms Reyes. I asked you on Monday to bring us something we can act on."

"Yes," she said. "Here it is."

---

She held up four fingers, because she'd decided at three in the morning that if it didn't fit on one hand it wasn't a plan.

"One. For every service where a failure could harm a patient, starting with Escalation and the eleven patient-identity services, one small team owns the whole thing, end to end. Three or four people, not fourteen, and one of them is clinical, someone who works on a ward and knows what it's like at the other end. Close enough to see all of it. Patient identity gets one owner, and that owner is a person, not a team."

"Two. Review is matched to risk, not applied uniformly. Most of what Digital does should carry on shipping exactly as fast as it does now, because most of it can't hurt anyone. But changes to safety-critical code are reviewed against the hazard, by someone with the authority to stop them. I'd like that to be a formal safety-review function with real authority, and I'd like Ruth Okafor to lead it." She didn't look at Ruth. She'd told her the night before, and Ruth had been silent on the phone for a long time and then said, *All right.* "If she says a change doesn't go, it doesn't go, and that isn't recorded against her rating."

"Three. Skills and prompts are treated as code. Every change to a shared Skill is tested before it goes into the library, against known cases, the way Mr Farouk tested `legacy-simplify` last Friday. Nothing comes in from public marketplaces unless someone has looked at it. And nobody gets to say *we ran it through the Skill* as if that settles anything. Whatever comes out of these tools is a proposal, and somebody checks it if it matters."

"Four. You protect the slow part on purpose. On safety-critical services, engineers get time to understand the system themselves, by working on it and not only reading it, even when an agent could do the work faster. I'd like to see graduate hiring restarted, with the people you hire actually taught. The skills that would have caught this were built by people doing the work slowly, for years, and you've been quietly removing every opportunity to build them. If you don't protect that deliberately, in five years there won't be anybody left who can tell when the machine is wrong."

She lowered her hand.

"And one more thing, which isn't a fifth point, it's how to do the other four," she said. "Don't do them everywhere at once. Pilot it on one team first, Escalation, and get it working. Learn what's wrong with it and fix that, and then spread it. I spent Monday night with a woman who runs a kitchen on exactly one principle. She never changes two things in the same week, so that when something goes wrong she knows which one did it. Every big transformation programme I've seen tries to change everything at once and then can't tell what worked." She paused. "Meridian has just shown you what happens when you change everything about how you build software in eighteen months and measure only the speed. I'd rather not do the same with the fix."

---

"That's four points," David said. "Not the whole problem. You said yourself the spend's out of control. And you told us the documentation had the warning in it four times and nobody read it. What's your fix for those?"

Maya had known this was coming. She'd spent an hour at two in the morning trying to write an answer to it, and had given up.

"I haven't got one," she said.

There was a small stir around the table.

"I'm sorry?"

"I don't have a fix for either of them. I don't think anybody does yet, anywhere." She kept her voice steady. "On cost, there's no accepted way to attribute AI spend to the value it produces, the way you would with headcount. The prices are moving every few weeks, and the vendor's pricing will change again in April. You've got one engineer spending two hundred and eighty times what another spends, and I can't tell you which of them is doing better work. Neither can anyone in this building. On documentation, the tools write accurately and at huge volume, in a voice where nothing sounds more important than anything else. The summariser turned a catastrophic warning into a green dot. It wasn't malicious, and I don't know how you stop it happening again. If I stood here and gave you a fix for either of those, I'd be making it up. You'd find that out the next time something went green that shouldn't have."

"Then what are you asking for?" David said. He sounded genuinely puzzled more than hostile.

"I'm asking you to own them," Maya said. "Formally. Put both problems inside the new safety-review function, with Ruth, so they're somebody's actual job and not a line in a risk register. Give that function the budget to work on them, to measure things nobody's measured: what changes cost, what fails, which warnings get read. And report back honestly on what it finds, including when it hasn't found anything yet. I'd rather you told the regulator you have two hard problems and a team working on them than told them you'd solved something you haven't."

Nobody spoke.

It was Felix who broke it, unexpectedly. He'd been sitting very still beside Ashworth for most of the presentation, his hands folded on the table in front of him, looking at Tariq's graph after it had gone from the screen.

"Can I say something?"

Pell nodded.

"I signed the budget paper," Felix said. "I chaired the calibration panel that moved Ms Okafor's rating down. I put an overnight agent loop on a slide at the all-hands as an example of what good looked like, and I held up Josh's team as the model for everyone else. I didn't read her steering paper, and I didn't ask what was on the conveyor belt, to use a phrase I've heard this week." He paused. He looked, Maya thought, older than he had two weeks ago, and more real. "I think I've been managing the engineering side of my job by looking at the only numbers I understood. I'd like to be the person who fixes that, if the board will let me. Not because I'm the right person to tell engineers what's safe. I'm clearly not. But somebody has to make Maya's four points actually happen, inside an organisation that's been built for the opposite, and I know where all the levers are, because I built most of them." He turned, slightly, towards Ruth. "And I'd need Ms Okafor to tell me what I can't see. I'd want to ask her first, before I assume."

It was the first thing Maya had heard him say, in two weeks, that wasn't designed to protect him.

Ruth looked at him.

"You can ask," she said. "I'll tell you."

---

Ashworth spoke last.

"I'll support this," she said. "All four points, piloted as Ms Reyes describes. Ms Okafor to lead safety review, reporting to me, not through Digital." She glanced at Felix, briefly. "Felix to lead the implementation. And I'll fund the safety function for a year to work on the two problems Ms Reyes says she can't solve." She turned to Pell. "I'd like the minutes to say that, Jonathan, in those words. *Two problems we are honest about not having solved.* I'd rather the regulator read that from us than worked it out for themselves."

Pell nodded slowly and made a note.

"David?" he said.

David Strand looked at Maya for a long moment across the table. He didn't smile.

"I think you've let a lot of people off," he said. "I haven't changed my mind about that. Somebody pressed the button." He picked up his pen and put it down. "But I'm not going to vote against it. We'll see in ninety days."

It wasn't a concession. It wasn't a defeat either. Maya, who had expected one or the other, found she was too tired to tell the difference.

---

Afterwards, in the lift, Ruth stood very upright against the mirrored wall with her notebook held against her chest.

"Are you all right?" Maya asked.

"Yes." Ruth was looking at the floor numbers counting down. "I sat at the table," she said, after a moment, as if checking the fact.

"You did."

"Nobody's ever—" She stopped. Then she shook her head slightly and didn't finish.

When the doors opened at the lobby, Marcus was standing just outside them with his canvas bag over his shoulder and the newspaper under his arm, folded to the crossword. It was finished.

He looked at Ruth first, not at Maya.

"Well?" he said.

"They're going to pilot it," Ruth said. "On Escalation. I'm leading safety review."

Marcus didn't say anything for a moment. Then he nodded, very slowly. Maya saw something move in his face, there and gone, thirty years old.

"Good," he said quietly. "Good."
