# Chapter 3 — The Assistant

Meridian Digital lived in a converted printworks behind King's Cross, three floors of exposed brick, standing desks and huge screens. It looked like a place where things got built, and it was deliberately unlike the hospital group that paid for it. On the ground floor there was a café with a barista and a wall of framed press cuttings. MERIDIAN LAUNCHES UK'S FIRST AI TRIAGE ASSISTANT AT SCALE. HEALTHCARE'S QUIET REVOLUTION. Maya counted nine before Felix Adeyemi came down the stairs two at a time to meet her.

"Maya. Felix. Thank you for doing this." He shook her hand warmly, as if she had come to invest rather than investigate. He was forty or so, tall, in a navy jumper over a collared shirt, with the relaxed energy of a man who had given a lot of keynote talks and enjoyed most of them. "I know why you're here. Terrible week. Terrible. Let me show you who we are first, so you've got the context. Ten minutes. Then whatever you need."

She had planned to say no. She said yes, partly because people told you a great deal in the ten minutes they chose for themselves, and partly because Felix was already walking.

He took her up to the second floor, to a team area beneath a hanging sign that read ASSISTANT in friendly lowercase. Twenty or so people worked at clusters of desks around a central screen that showed a live map of the UK, dotted with small pulses of light.

"Every one of those is a conversation," Felix said. "Right now. Somebody in Leeds asking whether they need to fast before their colonoscopy. Somebody in Bristol trying to understand a discharge letter. We handle about thirty thousand conversations a week. Patient satisfaction is eighty-eight percent. Call-centre volume is down a third. And the triage function," he tapped the screen, and a panel of numbers appeared, "is routing urgent symptoms to a human clinician in under ninety seconds. Ninety seconds, Maya. The old phone line averaged nine minutes."

"That's impressive," she said, and meant it.

"It's the reason I came here." He said it more quietly. "My dad had a stroke four years ago. He went to A&E with a headache and slurred speech, and he sat in a corridor for eleven hours because nobody joined up the dots. Every individual person did their job. Nobody saw the whole thing." He shrugged, as though it were a small story, and it plainly wasn't. "When people ask me why I care about this, that's why. Getting the right information to the right person fast enough. That's the whole job."

Maya looked at him and thought that he had just described Monday night precisely without knowing it.

He showed her the product. He opened the Assistant on his own phone and had a conversation with it about chest pain, and it asked him three sensible questions in a calm voice, recognised a red flag in his second answer, and told him clearly to call 999. He showed her the safety framework the clinical team had built around it: a library of over four thousand tested scenarios, a weekly review of every conversation the model had flagged as uncertain, and an escalation pathway to a duty clinician twenty-four hours a day.

"We had the regulator in last autumn," he said. "They called it the most rigorously assured AI product they'd seen in UK healthcare. We've been asked to speak at the NHS Confed on it."

"And it doesn't touch lab results."

"Never. It can't see them. It's a separate world." He put his phone away. "Which is why the press coverage this week is so frustrating. We've done this properly. We've been criticised for being too careful, honestly. And now people think the one AI system in the building that has a four-thousand-scenario safety case did this."

"So tell me about the system that did do it."

"Escalation?" There was a fractional pause. "Sure. What do you want to know?"

"What does it do?"

"It routes critical lab results to clinicians." He said it the way someone recites a line from a slide. "If a result is outside a safe range, it finds the right doctor and pages them."

"How does it find the right doctor?"

"It looks up the patient and their current admission and works out who's responsible." He made a small gesture, the kind people make when the answer is obvious. "Standard integration."

"Who built it?"

"Before my time. Twenty fifteen, I think, by a contractor. It's been maintained by Clinical Platform since."

"When did you last look at it?"

Felix laughed, not unkindly. "Maya, I have a portfolio of two hundred and something services. Escalation is plumbing. It's the kind of thing that's supposed to just work and that nobody ever thinks about, which is exactly how it should be. That's Josh's world. Josh Whitfield runs Clinical Platform. He's excellent. He'll be able to tell you everything."

"But you're accountable for it."

"I'm accountable for all of it." He said it easily, without hearing the weight it should have carried. "And I'm taking this extremely seriously. But I'd be lying if I said I could walk you through the code. That's not my role. My role is setting direction and making sure the teams have what they need."

"What do they need?"

His face lit up again, back on solid ground. "Tooling, mainly. Two years ago we made a decision that Meridian was going to be AI-first, not just in the product but in how we build. Every engineer in Digital has access to the best coding agents on the market. Unrestricted, more or less. We don't micromanage how people use them. Let smart people find their own way. That's been the philosophy, and it's worked." He walked her to a different screen near the stairs, an internal dashboard. "Look at this."

It was an adoption chart. A line climbed steeply from left to right across eighteen months, labelled *Active AI tool users, Digital Services*. Beneath it a second chart showed *Pull requests merged per engineer per week*, which had more than doubled. A third showed *Median cycle time*, falling.

"We're shipping more than twice as fast as we were two years ago, with roughly the same headcount," Felix said. "The board loves this chart. I love this chart."

Maya studied it. She'd been trained as an engineer before she was trained as anything else. The habit had never left her of looking at a graph and asking what it wasn't showing.

"Is everyone using it the same way?"

"God, no. That's the beauty of it." He scrolled. There was a breakdown by team, and then by usage band. "We've got some people who are absolutely all in. Running agents in parallel, automating their whole workflow, building their own tools on top. Honestly, some of them are doing things I don't fully understand, and I mean that as a compliment. Then there's a big middle that uses it day to day. Then there's a small group who use it a lot less."

"How much less?"

"A lot less." He hesitated. "There are a few senior engineers, mostly in Clinical Platform, who've chosen not to use agents for anything patient-facing. They've got their reasons. Background in regulated industries, some of them. We respect that. We don't force anyone."

"Do they agree with each other? The people who are all in and the people who've opted out?"

"About what?"

"About whether it's safe."

Felix looked at her as if the question hadn't quite parsed. "It's a tool, Maya. People use tools differently. Some carpenters like a nail gun and some like a hammer. You don't need them to agree."

"Unless they're building the same house."

He laughed. "Fair. Look, I'm sure there are robust conversations. Engineers love a robust conversation. But that's culture. That's healthy." He checked his watch, a slim, expensive thing. "Let me introduce you to Josh. He's expecting you. And Maya," he touched her arm lightly, "whatever you need, you'll have it. Access, people, data. I want this understood as much as anyone. We need to be able to say, clearly, that this was a contained issue with a legacy system, so the good work here isn't tarred with it."

She noticed the sentence. He had already decided the answer and was asking her to bring it back with a bow on.

---

Felix handed her off to his chief of staff, who walked her down a floor. The lower floor was quieter. The brick was the same and so were the screens, but the hanging signs were older, and there was no map of pulses on any wall. A sign above one cluster of desks said CLINICAL PLATFORM in a font that had been fashionable about five years ago.

While she waited for Josh, Maya took out her notebook and wrote down three things.

*Felix: genuinely good at product. Assistant appears robustly assured. Not the cause.*

*Felix: cannot describe Escalation beyond one sentence. "Plumbing." Accountable for it; has never looked at it.*

Then, after a moment:

*"Let smart people find their own way." Usage varies enormously. Some engineers opted out of agents for patient-facing work. Who? Why? Did anyone listen to them?*

She looked at the third note. It was the beginning of a thread, nothing more. The incident could easily turn out to be what it looked like from the twelfth floor in Paddington: one change, one person, one bad afternoon. Most were. She had a fortnight and a client who wanted a clean answer, and a clean answer was what she was good at.

She underlined *Did anyone listen to them* anyway.

Across the floor a man in his late thirties had stood up from a desk and was coming towards her, a laptop under his arm and his lanyard swinging. He had the slightly hunted, over-caffeinated look of someone who hadn't slept properly since Tuesday.

"Ms Reyes? Josh Whitfield." He held out his hand, then seemed to realise he was holding his laptop in it and swapped. "Sorry. It's been a week. Do you want the numbers first, or the code?"
