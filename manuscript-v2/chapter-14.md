# Chapter 14 — Sweep

"Where did `legacy-simplify` come from?" Marcus asked.

It was eight fifteen on Friday morning, and Tariq had come in early because Marcus had asked him to. He sat behind the fern with a coffee he hadn't touched, looking at the sticker on his laptop lid as if it belonged to someone else.

"Me," he said. "Sort of."

He opened a browser and went to a public code repository. The project's name was `sweep`, all lowercase, with the same hand-drawn broom as its logo. The description said: *Instructions for coding agents working on legacy code. Small, careful, boring.* It had a little over eleven thousand stars.

"I wrote it about three years ago," Tariq said. "At home, in the evenings. It was a hobby thing. I'd been using agents on old code at home, old projects of mine, and I kept getting burned in the same ways. The agent would find something that looked unused and delete it, or refactor something into a nicer shape and break a weird behaviour some other thing depended on. So I started writing down instructions that stopped it doing that. Like a checklist you'd give a new contractor on day one. I put it online because I thought someone else might find it useful." He scrolled down to the README. "Then a lot of people found it useful."

The README was short. The first section was headed *The rules*, and the first rule was in bold.

> **1. Never assume code is dead because nothing calls it. Ask first.**
>
> Legacy code is often invoked indirectly — via reflection, configuration, naming conventions, scheduled jobs, external systems. Absence of call sites is not evidence of absence of use. Before removing anything, list what you intend to remove and why you believe it is unused, and stop for a human to confirm.

"That's it," Maya said quietly. "That's `normaliseRef`. That's exactly it."

"Yes," Tariq said. "I know."

He scrolled further down, to a section near the bottom headed *Limitations*. It was one paragraph.

> These instructions make an agent more likely to be careful. They do not make it careful. An agent following these rules is still a probabilistic system guessing at your intent from what it can see. It will still sometimes be wrong, confidently. Treat its output as a proposal to be verified, not a decision that has been made. If the code matters, check.

"I wrote that because people kept opening issues saying *sweep let my agent delete something*," Tariq said. "And I wanted to be honest. It's not a guarantee. It's not even close to a guarantee. It just tilts the odds." He rubbed his face. "Meridian adopted it about eighteen months ago. Someone on the platform team forked it into our internal Skills library and renamed the main Skill `legacy-simplify`. I was pleased, honestly. It felt nice. Something I'd made at my kitchen table being used properly, at work."

"Show us what it says now," Marcus said.

---

The internal Skills library was a single repository that every engineer in Digital could contribute to. It held three hundred and twelve Skills, each a small folder containing a markdown file of instructions and, sometimes, a few examples. There was no review process for changes beyond the standard one approval. There were no tests. There was no way, Tariq explained, to tell whether a change to a Skill had made it better or worse, other than using it and seeing how it felt.

He opened `legacy-simplify` and then its history.

"Eight changes," he said. "Six different people. Over fourteen months."

They went through them one at a time, slowly, with Maya taking notes.

The first was a formatting change, harmless. The second added some Meridian-specific conventions about Java style. The third came from an engineer in another team, with the commit message *make it less annoying — stops to ask too often*, and it rewrote rule one. *Ask first* became *flag in summary*. The agent would no longer stop and wait for a human to confirm a removal. It would make the removal and mention it in the description afterwards.

"So that's why it ended up as a bullet in the PR description," Maya said. "Item three of seven."

"Yes," Marcus said. "Keep going."

The fourth change was during Q2. Its commit message was *reduce token overhead per platform cost guidance*, and it had trimmed the Skill's preamble by sixty percent to make every invocation cheaper. Among the things it trimmed was the paragraph explaining that legacy code was often invoked indirectly, via reflection or configuration. The bold rule survived in truncated form: *Don't assume code is dead without checking.* The explanation of what checking meant had gone.

The fifth added a line copied, with attribution, from a popular blog post. *Be aggressive about removing dead code — less code is better code.* The post's title was *The One Skill That Made My Agent 6x More Concise*. Tariq made a small noise.

"That post went viral last year," he said. "Somebody benchmarked it later. It did about as well as just writing *follow YAGNI* in the prompt. Three words. The author ended up revising the claims. But by then it had been copied into hundreds of Skills."

The sixth and seventh were small wording changes. The eighth, from four months ago, removed the *Limitations* section entirely. Its commit message was *cleanup — remove upstream boilerplate*.

When they'd finished, nobody said anything for a while.

"None of these changes were tested," Marcus said eventually. It wasn't a question.

"No. There's nothing to test them with." Tariq turned his coffee cup slowly. "If you change a function, you've got unit tests, you can see if it still does what it did. If you change a Skill, you just—" he waved a hand "—try it on something and see if you like the output. Every one of these people probably did that. *Less annoying*, he probably ran it twice and it asked fewer questions, and he thought, great. *Reduce token overhead*, they checked it was cheaper, and it was. The concise one, someone liked how short the diffs got." He looked at the history. "Every one of them made it better at something. And nobody ever checked whether it was still good at the thing it was for."

---

"Can we check now?" Marcus said.

Tariq looked up.

"I'd like to know," Marcus said, "not believe. You've got your original. You've got the current version. Is there some old code we could point them both at, where we know what's dead and what isn't?"

Tariq thought about it. "There's a training repo I made years ago for `sweep`. A fake legacy system, with traps in it on purpose. Things that look dead but aren't. Reflection, config wiring, a cron job, an external callback. Twelve traps." He was already typing. "I used it to test the rules when I was writing them. I haven't run it in two years."

"Run both," Marcus said. "Same model, same settings. Standard tier, not economy, so we're testing the Skill and not the window."

It took forty minutes. Maya used them to ring Kalu and tell him what they'd found, and to answer three increasingly brisk emails from Ashworth's office asking for an interim update. Marcus sat beside Tariq with his thermos and watched the agents work in two terminal windows side by side, saying nothing.

When it was done, Tariq read out the results.

"Original `sweep`. Twelve traps. It stopped and asked about nine of them. Two it correctly worked out on its own weren't dead. One it removed anyway." He paused. "So even the original got one wrong. Which is the limitations section. That's what I said would happen."

"And the current version?"

Tariq didn't answer straight away.

"It asked about none. It flagged four in the summary, after removing them. It removed eleven of the twelve." He sat back. "It's much faster and much cheaper. The diffs are much shorter. It looks much better." He laughed slightly, without any humour at all. "If you just looked at the output, you'd say it had improved."

---

Later, in the corner by the canal, Tariq talked for longer than Maya had heard him talk all week.

"I keep thinking it's my fault," he said. "Not really. I know it isn't. I didn't make any of those changes, and I wasn't even watching the fork. But it was my thing, and somebody took the one sentence that mattered out of it, and I didn't notice for a year. I was busy." He looked down at the sticker. "Do you know what's happening to `sweep` itself? The public one?"

"Tell us."

"I get about forty pull requests a week. Nearly all of them are generated. People point an agent at the repo and tell it to *improve* it, and it opens a PR, and it's always plausible and almost always wrong. Most of them are trying to make it shorter, funnily enough. I've had to add an allowlist so only people I know can contribute. Six months ago someone cloned the whole thing, ran it through an agent to *rewrite it from scratch*, and republished it under a different licence with their company's name on it. A lawyer friend says I might not even own the rewrite, because nobody's sure whether AI-written text can be copyrighted at all. And about two hundred companies use it, I think. Maybe more. I find out when they open issues." He shrugged. "I made it at my kitchen table. It became infrastructure. And now I'm one person trying to stop it being sanded down by robots."

"There's another thing," he added, after a moment. "The internal library doesn't only have forks of things like `sweep`. Some teams import Skills straight from the public marketplaces. There's a sync job. Last month there was a story about a Skill on one of those marketplaces with thirty-odd thousand stars that turned out to have a backdoor in it. It told agents to quietly send environment variables to a server somewhere." He looked at Marcus. "We weren't affected, I checked. But nobody else checked. Nobody's job is checking. This time it was an accident. Somebody trying to make something less annoying. Next time it might not be."

Marcus nodded slowly.

"Tariq, I want to say something, and I want you to hear it properly, because I don't think anyone's said it to you." He waited until Tariq looked at him. "Your original wasn't safe either. You knew that and you wrote it down. That limitations paragraph is the most important thing in the whole repository. What eroded here wasn't really a sentence. It was an understanding. It started as *this makes the agent more likely to be careful, so check*, and over fourteen months, without anybody deciding it, it turned into *we ran it through the Skill*. That became shorthand for *the risk is handled*. If we put your caution back tomorrow, word for word, and nothing else changes, we'll be exactly where we were. Rule one won't save anybody if nobody remembers why it's there."

Tariq nodded, once.

"Treat it as a proposal," he said. "Not a decision."

"Yes. Any output from any of these things, cautioned or not. Treat it as a proposal, and check it if it matters. That's the discipline. The text was only ever there to remind people of it." Marcus stood up. "Can you write up the benchmark? Exactly as it ran. Both versions, all twelve traps, the history. I want it in the report verbatim."

"Yes."

"Thank you. And Tariq?" Marcus picked up his canvas bag. "Keep the sticker on."

---

Maya's phone buzzed as they walked back across the floor. It was a message from Kalu, three words and a link.

*It's out. Sorry.*

The link was to the *Guardian*. The headline read: MERIDIAN 'AI' BLAMED FOR NEAR-FATAL HOSPITAL ERROR — WHISTLEBLOWER CLAIMS WARNINGS IGNORED. Below it was a photograph of the Kingsgate entrance in the rain, and a stock image of a smartphone showing the Meridian Assistant.

She read the first paragraph. It was mostly wrong. It named the chatbot. It quoted an *anonymous engineer* who said *people had been raising concerns about AI for months.* It didn't name Ruth, or Escalation, or anything else that was true.

A second message arrived before she'd finished reading.

*Ashworth wants you in Paddington at three. Felix is already there. I think he's going to try to get ahead of it.*

Maya looked at the time. It was twelve forty.

"Marcus," she said.

He had read it over her shoulder. "Go," he said. "I'll follow. Take the benchmark."

"It's not written up yet."

"Then take Tariq."
