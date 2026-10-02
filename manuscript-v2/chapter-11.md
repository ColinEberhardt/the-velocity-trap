# Chapter 11 — The Shape of Things

Tariq Farouk sat at the end of a row of desks on the platform team's side of the floor, half-hidden behind two monitors and a large potted fern that had clearly been there longer than anyone else. He was in his late thirties, slight and quiet, in a faded T-shirt and a fleece. His laptop lid had a single sticker on it, a small hand-drawn broom with the word `sweep` underneath in lowercase. He looked up as they approached with the expression of a man who had been expecting a knock on the door for some time.

"Josh said you might come," he said.

"Josh said you know the dependencies better than anyone," Marcus said.

Tariq made a small, pained face. "That's not as much of a compliment as it sounds."

"Why not?"

"Because I'm the only one who tries."

The official architecture diagram for Digital Services lived on the internal wiki. Tariq brought it up first, almost apologetically, so that they would understand what he was about to show them. It was a large, handsome thing: two hundred and eleven boxes in tidy colour-coded swimlanes, connected by neat orthogonal arrows. At the top it said *Last updated* and a date fourteen months ago.

"That's what we show auditors," Tariq said. "It was accurate once. For about a week."

"And now?"

He hesitated, then opened a different window.

It wasn't handsome at all. It was a sprawling force-directed graph, hundreds of nodes pulled into dense clusters by thousands of thin grey lines, with a few clumps so crowded they'd turned almost solid. It looked less like a diagram than a photograph of something growing.

"I built a script," Tariq said. "It crawls every repo every night and works out what actually calls what. Not what the docs say, what the code says. Imports, API calls, shared database tables, config references. It's not perfect. But it's closer than that." He nodded at the wiki window. "I started it about two years ago, when I realised nobody could answer a question I had. I've been running it ever since. I don't really show it to people."

"Why not?" Maya asked.

Tariq considered the question as if it were a technical one.

"Because the first time I showed it to someone, in a team leads' meeting, everyone said *wow* and asked me to make it look nicer. And the second time, people asked whether it was really my job to be doing it." He shrugged. "So I just kept running it."

"What was the question?" Marcus said. "The one nobody could answer."

"How many things in Meridian know how to work out who a patient is."

---

He showed them.

He typed a query, and most of the graph faded to grey. What remained were eleven nodes, scattered across the canvas in four different clusters, each lit up in orange.

"These are all the services that do their own patient-identity matching," Tariq said. "Each one takes some kind of reference, an MRN, an NHS number, a name and date of birth, and resolves it to a patient. In theory there's one shared identity service for that, which Clinical Platform owns." He pointed to a large node near the centre. "In practice there are eleven separate implementations."

"Eleven," Maya said.

"Some of them are copies of each other. Some are copies of copies. Escalation's is the oldest." He clicked on it, and a thin orange thread lit up running from it to three other nodes. "These three were copied from Escalation's at some point. Probably by an agent. When you ask an agent to build a feature that needs patient lookup, it'll often write a new one. It's quicker for it to write fresh code than to work out how to use the shared library properly, so that's what it does. Nobody notices, because it works, and the tests pass. And six months later you've got another one." He clicked again. "These four are separate lineages. And these were written by hand, years ago, by different teams for different reasons."

"Do they all handle merged records?"

Tariq was silent for a moment.

"I don't know," he said. "That's what Josh asked me on Monday. I've been looking at it since. I think five do it properly, through the shared service. Two do it their own way, and I'm not sure if their way is right. Four don't handle it at all, as far as I can tell. Whether that matters depends on what they're used for, and for some of them I don't know what they're used for." He looked at the orange dots. "I didn't tell Josh yet. I wanted to be sure. I'm not sure. I don't think I can be sure, actually, which is what I was going to tell him."

Marcus pulled a chair over and sat down beside him, looking at the graph.

"Who owns patient identity at Meridian?" he asked.

"The identity service is Clinical Platform's."

"I didn't ask who owns the service. I asked who owns patient identity. If I wanted to know, today, every place in this organisation where a patient's record could be misidentified, who would I ask?"

Tariq took a while to answer.

"Nobody," he said. "You'd ask eleven teams, and they'd each tell you about their bit. And none of them would know about the other ten."

---

Marcus sat back.

"There's a study I like," he said. He said it to Maya, but Tariq was listening. "Researchers took eight hundred and six open-source projects that adopted one of the AI coding tools and compared them against projects that didn't, over time. In the first few months, the projects that adopted the tools moved faster. About fifteen percent faster, measured on commits and features. You'd expect that. But they also measured the code. Static-analysis warnings, complexity, duplication. It got worse, and steadily so. Over time the quality loss ate into the speed gain, because every change got harder to make safely." He looked at the graph. "That's eight hundred and six projects, so it isn't my opinion. And those were open-source projects, mostly small teams who could actually see their own code. This is six hundred engineers and two hundred services. Nobody can see the whole of it, apart from one man running a script he's been told isn't his job."

"So it's not a failure in Escalation," Maya said. "It's a failure of shape. The organisation's been producing code faster than anybody can see where it's going."

"It's both. Escalation's the place it came out." Marcus nodded at the cluster of orange. "When things drift this fast, the system stops having a shape anyone can hold in their head. And when nobody can hold the shape, nobody can see when part of it is wrong. You'd have to be close enough to notice, and nobody here is close enough to anything any more."

Tariq was looking at his own screen as though seeing it for the first time.

"I used to know all of this," he said quietly. "When I joined, six years ago, there were about forty services. I knew them all. I could tell you who'd built each one and why. I could draw it on a whiteboard from memory." He rubbed his eyes under his glasses. "Now I come in and there are three new services I've never heard of, generated over a weekend by someone in another team, and they're already in production, and they're calling something of ours. And it all works. It all works fine. Everyone's very busy and very productive and building lots of things." He stopped, and seemed for a moment to be talking to himself. "Half the time I'm not sure I know what I know any more."

There was a brief pause. Then he blinked and gave a short embarrassed laugh, and turned back to his keyboard.

"Sorry. Ignore me. Long week."

Maya glanced at Marcus. He didn't react, and after a moment neither did she. Later, in the lift, she wrote the sentence down without quite knowing why.

---

"I'd like you to tell Josh," Marcus said, standing up. "Today. All of it, including the four you're not sure about and the fact that you can't be sure. And then I'd like you to send the same thing to the clinical safety team, so they can decide which of those four matter."

Tariq nodded. "Okay."

"And I'd like a copy of the graph."

"It's not finished. It's not really—"

"It's the only accurate picture of this organisation I've seen since I arrived," Marcus said. "I'd like a copy."

Tariq looked at him and something in his face eased slightly. "Okay," he said again. "I'll send it."

As they left, Maya glanced back. Tariq was still looking at the graph, at the eleven orange nodes, and then he dragged one of them a little way across the screen and let it go. It sprang back into its cluster, pulled by all the lines attached to it.

---

They walked back to their corner. Nine days now. Maya could feel the number sitting at the back of her head like a headache.

"We came here to find out how one change got through," she said. "Now I've got eleven services that might have the same problem, four of which nobody can tell me anything about. I've got a risk register that swallows warnings and a spend distribution nobody's looked at. I've got a budget paper that measured the conveyor belt, and a cost cut that took away the agent's peripheral vision." She sat down. "And I've got nine days to give a board something it can act on."

"What are you going to give them?"

"I don't know yet." She took her glasses off and turned them over in her hands. "I know what I'm not going to give them. I can't stand up there and say *one junior engineer made one mistake* now. Not after this."

"Good."

"Ashworth's going to hate it."

"Ashworth's going to hate it until the moment she realises it protects her," Marcus said. "Then she'll believe she thought of it." He took out the thermos. "Tomorrow I want to look at the review. Not the four minutes. I want to know what review is *for* here. What people think it's for. I suspect they don't agree."

"Callum."

"Callum. And whoever's been arguing with him." He poured the tea and looked across the floor, where Ruth was at her desk under the window again, writing. "I suspect I know who that is."
