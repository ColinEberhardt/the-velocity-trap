# Chapter 4 — Clinical Platform

Josh wanted to give her the numbers first. Maya let him. She was sizing him up the way she'd sized up Felix, by watching what he reached for when he was frightened.

They sat in a meeting room called Fleming, named, like every room on the floor, after a scientist. Josh plugged his laptop into the screen and brought up a team dashboard before she'd taken her coat off.

"So, context," he said. "Clinical Platform is nine services, fourteen engineers. We own the stuff between the clinical systems: lab integration, results routing, Escalation, bed management feeds, a couple of identity services, the observations pipeline. None of it's glamorous. All of it's important." He clicked. "Over the last eighteen months, our throughput is up two hundred and ten percent. Deployment frequency up from weekly to multiple per day. Change failure rate, before Monday, was under two percent. Mean time to restore is under an hour. On the DORA metrics we're comfortably elite."

"Before Monday."

He stopped. "Yes. Before Monday."

He kept his eyes on the screen for a second too long. Then he closed the dashboard and opened a terminal, and his voice changed. It got quieter and more careful, the voice of someone who had been over the same ground two hundred times since Tuesday.

"Okay. Here's what happened."

He walked her through it, and to his credit he did it well. The result came in from the lab carrying the patient reference printed on the sample. Escalation looked that reference up in the master patient index to find the patient's current admission. That was where it went wrong. Mr Hale had two records. One had been created by mistake at a clinic in Watford, with his name abbreviated and two digits of his date of birth the wrong way round. When someone spotted the duplicate, the two records were merged. The Watford record was retired. It still existed, but it now carried a pointer to the real one.

"The blood sample was ordered from his pre-op order set," Josh said, "which still had the old record on it. Nobody updated it after the merge. So the lab sent the result against the retired number. That happens. It's not common, but it happens."

"And Escalation used to handle it?"

"Used to." He pulled up a diff. On the left was old code, a dense method thirty lines long with a name that told her nothing: `normaliseRef`. On the right was nothing at all. "This was the bit that handled it. It looked up the reference, and if it found a retired record, it followed the merge pointer to the live one. Then it carried on as normal: found the admission, found the ward, found the doctor, paged them."

"And now?"

"Now it's gone. Without it, a retired record has no active admission. Escalation does what it's been told to do when there's no active admission, which is send the result to the inbox of whoever ordered it." He swallowed. "Which was the Watford pre-op clinic. Which closes at five."

Maya looked at the empty right-hand side of the diff.

"When was it removed?"

"Six weeks ago. January twelfth. Pull request four-four-seven-one." He brought it up: a title, a description, a list of files. *Simplify legacy patient matching in Escalation; remove dead code paths.* Minus two thousand one hundred and forty lines, plus three hundred and eighty. "It was part of a modernisation pass. Escalation's the oldest thing we own and it's a mess. A lot of it really was dead. We were cleaning it up."

"Why did it look dead?"

"Because nothing calls it." Josh rubbed his face. "Not directly. It's wired in through a config file, a handler map, from an old pattern nobody uses any more. If you search the code for anything that calls `normaliseRef`, you get nothing. Static analysis flags it as unused. To be honest, if you'd shown it to me cold, I'd probably have flagged it too."

"Who wrote it?"

"No idea. Twenty seventeen. A contractor, the commit history says, and the commit message is literally just *fix*. No ticket. No documentation. No test."

"No test?"

"No test that covers a result arriving against a merged record. We had good coverage on Escalation, eighty-something percent. Just not on that." He held her gaze, and she saw what it cost him. "So the tests all passed. The build went green. It went out with eleven other changes that afternoon, and nothing happened for six weeks, because merged records with a live critical result are rare. Until Monday."

"Who made the change?"

He'd known the question was coming and still flinched.

"One of my engineers. Sam Ilyas. He's—" Josh hesitated. "He's very good. He's junior, but he's good. He used our standard tooling, the coding agent and a Skill from our internal library that's designed for exactly this sort of legacy cleanup. He raised the PR. It was reviewed and approved. It went through the pipeline. It did everything the process asked it to."

"I'd like to talk to him."

"He's here." Josh looked through the glass wall of Fleming towards the desks. "We've stood him down from production access, which is standard. He asked to keep coming in. I think he'd go mad at home."

---

Sam Ilyas was twenty-four and looked younger. He came into Fleming holding a mug of tea he didn't drink and sat on the edge of the chair, as if he might be asked to leave at any moment. He had a lanyard with a picture on it that must have been taken on his first day, smiling at the camera with a kind of startled hope. The person in front of Maya now didn't look much like it.

"Thanks for talking to me," she said. "This isn't a disciplinary interview. I'm not part of HR. I'm trying to understand what happened."

"Yeah. No. Of course. Sorry." He put the tea down. "Sorry. I just want to say first, I know it was my PR. I'm not trying to say it wasn't. I've read about him. Mr Hale. I just—" His voice gave out and he pressed his lips together. "Sorry."

"You don't need to apologise to me."

"I know. Sorry." He laughed shakily at himself. "I do that."

She asked him to walk her through how the change had happened, and he did. He'd been given a modernisation ticket for Escalation's patient-matching module, one of a series Josh had broken out to clean up the oldest services. He'd used the coding agent, like everyone did, and run the `legacy-simplify` Skill over the module, like the ticket suggested. The agent had produced a plan, then a diff, then a summary of what it had changed and why. He'd read the plan. He'd read the diff.

"All of it?"

"Yeah. Every line." He said it with a kind of desperate precision. "I always do. People tease me about it. It took me most of the afternoon, which is slow, I know, for a change like that. I checked that the tests passed. I ran it locally. I checked that the stuff it said was dead really didn't have any callers, and it didn't, I searched for it. I didn't know about the config file. I didn't know it was wired in like that." He looked at his hands. "I should have known."

"How would you have known?"

"I don't know. Someone would have known. Someone more senior." He shook his head. "Someone who'd been here longer would have looked at it and gone, wait, what's that, that looks weird, and gone and found out."

"Did anyone more senior look at it?"

"Callum approved it. He's really good. He's been here four years." Sam winced. "I'm not saying it was his fault. It was mine. It was my PR."

Maya let a silence sit for a moment. In her experience people often told you the true thing just after the moment when they'd finished telling you the prepared thing.

"When you read the diff," she said, "every line, all afternoon, did you feel like you understood it?"

Sam opened his mouth, closed it, and looked at the window. When he spoke again it was slower, and the apologetic edge had gone out of it. Later, she would remember that.

"Kind of," he said. "I mean, I understood each bit. I could tell you what each line did." He frowned, picking at the edge of the lanyard. "I read every line. I just never really know, with any of it, whether I actually know."

He seemed to hear what he'd said and looked up quickly, embarrassed.

"Sorry. That sounds weird. I just mean it's a big codebase. You know."

"Sure," Maya said.

She wrote the sentence down anyway, word for word, in her notebook. She didn't know why, except that it was the first thing anyone at Meridian had said to her all day that didn't sound as if it had been rehearsed.

---

Afterwards she sat in Fleming on her own for twenty minutes and drafted the report in her head.

She could see it, because she had written it eleven times before. A junior engineer, inexperienced with a legacy system, used AI tooling to remove code he incorrectly believed to be unused. The reviewing engineer approved the change without detecting the dependency. There was no test coverage for the affected scenario. Root cause: inadequate understanding of a safety-critical dependency, compounded by insufficient review. Recommendations: mandatory senior review for changes to safety-critical services; improved test coverage; training on legacy-system risk.

It was true. Every word of it was defensible. Ashworth would read it in eight minutes and thank her, and the regulator would accept it. Sam would probably lose his job, or keep it and wish he hadn't, and the press would print *junior engineer error* under the chatbot headline. Within a month everyone at Meridian would have quietly agreed that the problem had been found and fixed.

She took her glasses off and pressed the bridge of her nose.

The trouble was that the report explained the change, and it didn't explain the code. Somebody in 2017 had written thirty lines of life-or-death logic, named them `normaliseRef`, wired them in somewhere nobody would think to look, and left a commit message that said *fix*. For nine years after that, an organisation that ran fourteen hospitals had kept that logic alive without anybody writing down what it was for. Then, six weeks ago, a well-meaning twenty-four-year-old and a piece of software had removed it in an afternoon. The pipeline approved it, the tests approved it and a senior engineer approved it, in a process Josh's dashboard called elite.

She thought about Sam, reading every line, all afternoon, and still not knowing whether he knew.

Was that a junior engineer's problem?

She looked out through the glass at the floor. It was nearly six. Most of Clinical Platform had gone home. At a desk at the far end, under a window, a woman in her fifties was still working. She sat very upright, with a paper notebook open beside her keyboard, and every so often wrote something in it by hand.

"Who's that?" Maya asked Josh as he came back in to collect his laptop.

Josh followed her gaze. A brief, complicated expression passed over his face. It was the look of a man who has just remembered something he would prefer not to.

"That's Ruth," he said. "Ruth Okafor. Senior engineer. She used to work on Escalation, actually." He picked up the laptop and didn't quite meet Maya's eye. "She's on test tooling now."
