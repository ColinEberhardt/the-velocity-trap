---
layout: chapter
title: "Nobody Owns the Whole of It"
chapter_number: 11
permalink: "/chapters/11/"
prev: "/chapters/10/"
next: "/chapters/12/"
---

Tariq Farouk worked from the smallest desk on the floor, tucked behind a pillar in a way that struck Maya less like modesty and more like a man who'd chosen his own blast radius carefully.

"Platform team," he said, when Marcus asked what he actually did, in the tone of someone who'd learned the question never quite had a satisfying answer and had stopped trying to give it one. "I keep the plumbing working so everyone else's features can ship. Nobody thinks about plumbing until it backs up."

"Draw us the plumbing," Marcus said.

Tariq looked at him for a second, then did something Maya hadn't expected: he laughed, once, short and surprised, like a man who'd been asked a question nobody had bothered to ask him in longer than he cared to admit. "Nobody's asked me to do that in about a year."

He didn't open the official architecture diagram — Maya had already seen it, in the data room, dated fourteen months ago, boxes and arrows that had the specific unearned confidence of a document nobody had corrected since the day it was drawn. Instead he opened something of his own: a dependency graph he'd apparently been maintaining privately, scraped nightly from the actual codebase rather than from whatever anyone remembered building.

It looked nothing like the official one.

"This is current, as of this morning," Tariq said. "This is what's actually calling what. Nobody signed off on it looking like this. It just — got here, one team's fast decision at a time." He traced a cluster with his finger. "This whole section, patient identity and matching, used to be four services with a single owner. Now it's eleven, because four different teams have each built their own version of 'the bit that figures out who this patient actually is,' because it was faster to write a new one with an agent than to go and understand someone else's, and nobody stopped anyone, because there wasn't a version of 'stop' built into how fast we were all moving."

"Including Escalation's matching logic," Maya said.

"Including Escalation's matching logic. Which — for what it's worth — I didn't know had its own bespoke version until I built this graph properly last month, out of curiosity, on a weekend, because I wanted to know how bad it had actually got." He said it without any particular alarm, the flat delivery of someone reporting a fact he'd already made his peace with. "I found out along with everyone else, after."

Marcus studied the graph for a long moment, hands in his pockets, not touching the screen. "There's a study," he said, mostly to Maya, "eight hundred and six repositories, all recently adopting exactly this kind of tooling. Short-term velocity up fifteen per cent. Code quality — measured, not felt — worse every month after, compounding. Everyone in this building would tell you they're moving faster. They'd be right. Nobody would tell you what it's costing them to move that fast, because nobody's built the instrument that measures it, the way Tariq just had to build his own graph on a Saturday because the real one didn't exist."

"I don't think anyone's hiding it," Tariq said, a little defensive on his colleagues' behalf, though not, Maya noticed, on his own. "I think everyone's just — busy. Shipping their bit. It's not that people don't care about the whole system. It's that nobody's job is the whole system anymore, so nobody looks at it, so it drifts, and you only find out how far it's drifted when something like this happens." He gestured, vaguely, at the building around them, at the whole mess of it.

"Does that bother you?" Maya asked. "Not owning the whole of it."

He considered the question longer than she expected. "Sometimes. Most days I don't think about it — you get used to your little corner, you get good at your little corner, it's satisfying in its own way." A pause, and something crossed his face that he visibly decided not to chase any further, filing it away the way you file away a thought mid-sentence when you're not ready to finish it out loud. "Some days it just feels like everyone's very busy building something nobody can actually see the shape of anymore. But that's probably just a Tuesday feeling. Ignore me."

Maya didn't ignore it. She wrote it down, almost exactly, and didn't say anything, because she'd learned in the last week that the sentences people tried to wave away themselves were reliably the ones worth keeping.

"One more thing," she said instead, nodding at the graph. "Who else has seen this?"

"Nobody. It's not really — it wasn't for anyone. I just wanted to know." Something almost like embarrassment. "Is that bad?"

"No," Marcus said, before Maya could answer. "That's the only reason it's honest. The moment you'd built it *for* someone, you'd have started deciding what to leave out."
