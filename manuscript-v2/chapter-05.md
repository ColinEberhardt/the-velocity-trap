# Chapter 5 — R-117

Ruth Okafor didn't look up until Maya was standing right beside her desk, and even then she finished the sentence she was writing first.

The notebook was a hardback A5, black, with the pages numbered by hand in the top corner. Her handwriting was small and very even. Maya caught the words *timing assumption* and *verify against spec* before Ruth closed it, unhurriedly, and put her pen on top.

"You're the investigator," Ruth said.

"Maya Reyes. Kestrel Advisory."

"Ruth." She didn't offer her hand, but she didn't seem unfriendly. She had the composure of someone who had been waiting for this conversation for three days and had decided in advance how to have it. "Josh will have told you I used to work on Escalation."

"He did. He didn't tell me much else."

"No." It wasn't quite a smile. "I don't suppose he did."

Maya pulled out a chair from the next desk and sat, which Ruth noticed and allowed.

"I'm trying to understand how a piece of code that matters that much ended up with nobody knowing what it did," Maya said. "Did you know what it did?"

Ruth looked at her for a long moment. Maya had the sense of being assessed, quietly and thoroughly, the way an engineer looks at a component someone else has specified before agreeing to put it in her design.

"Can I ask you something first?" Ruth said.

"Of course."

"Who are you working for?"

"Meridian's chief executive."

"And what does she want you to find?"

Maya considered several answers and gave the true one. "She wants to know whether this was one person's mistake or something that's going to happen again. She'd prefer the first. Most people would."

Ruth nodded slowly, as if that matched what she'd expected and she respected Maya slightly more for saying it.

"There's a man in intensive care," Ruth said. "I don't want to be the person who stands next to his bed saying *I told you so*. That's not useful to him and it's not useful to anyone." She paused. "But yes. I knew what it did."

She opened a drawer and took out another notebook, an older one with a worn spine, and turned to a page near the middle without searching for it. She turned it round so Maya could read.

It was dated nearly two years earlier. At the top, underlined: *Escalation — patient-matching — normaliseRef (handlers.yaml line 212).* Below it, in the same small hand, a page and a half of notes. *Invoked via legacy handler map, not direct call. Resolves retired MPI refs via merge chain. No tests. No docs. Commit 2017, no ticket. Appears to be fix for an earlier incident? Ask around.* Then, further down, a later entry: *Asked M. in lab systems. Yes. 2017 near-miss, critical sodium, merged record, found by phone call from biochemist. Contractor patched. Never written up formally.* And finally, boxed: *DO NOT REMOVE WITHOUT EQUIVALENT. Must be documented before any refactor.*

Maya read it twice.

"You found this on your own?"

"I was working on a timing bug in the acknowledgement window and I traced a result that went somewhere I didn't expect. That's how you find most things in old systems. You follow one thread and it goes somewhere strange." Ruth took the notebook back. "I wrote it down because I write everything down. It's a habit from my previous job."

"Which was?"

"Fifteen years in medical device firmware. Infusion pumps, mostly. If your code controls how fast morphine goes into a child, you learn to write down everything you find, because the regulator will ask, and because one day you'll be the one who's forgotten." She said it plainly, without any drama. "When I came into healthcare software I was surprised how differently software is treated from devices. Something that would need a design history file and a verification plan in a pump goes out here on a Tuesday afternoon because someone said it looked fine."

"Did you tell anyone? About this?"

"Yes."

"Who?"

Ruth took a breath and let it out.

"Everyone I was supposed to."

---

The rest of it took Maya most of Friday, and most of Robert Kalu's goodwill, to put together.

Ruth had done more than write it in her notebook. Eleven months earlier, when the modernisation programme for Clinical Platform's oldest services was first announced, she had raised a formal risk in the Digital Services risk register. Kalu's office pulled it for Maya within an hour of her asking, and she read it on a laptop in a small airless room on the twelfth floor in Paddington, with the rain running down the window.

*R-117. Raised by: R. Okafor. Service: Critical Results Escalation.*

*Description: Escalation's patient-matching module contains undocumented, untested legacy logic (normaliseRef) that resolves retired/merged patient records to the surviving record. It is not called directly and will appear unused to static analysis and to AI coding agents. If it is removed or altered during modernisation, critical results for patients with merged records will fail to route to the responsible clinician. Results will appear delivered.*

*Impact: Catastrophic (missed critical result; potential death).*

*Likelihood: High if modernisation proceeds via AI-assisted refactoring before this behaviour is documented and covered by tests.*

*Proposed mitigation: Before any refactor of Escalation patient-matching, (1) document all legacy matching behaviour, including merge-chain handling; (2) add tests covering merged/retired records; (3) require review by an engineer with knowledge of this module. Estimated effort: two weeks.*

Maya read it, and then read it again, and then sat back in the chair.

The register showed what had happened next. The risk was assessed by the programme. Its likelihood was revised from *High* to *Medium* with the note *mitigated by existing test coverage and code review*. Its owner was changed from Ruth to *Clinical Platform (team)*. The two weeks of documentation work was added to the backlog, given a priority of *Should*, and never picked up. The last update, four months ago, said only *Remains open. Will address as part of modernisation.*

Every step of it was reasonable, Maya thought. No one had refused anything, and no one had said no. The risk had been accepted, recorded, reassessed, reassigned and scheduled, and the organisation had then got on with its work. It had all been done the way it was supposed to be.

"There's more," Kalu said, from the doorway. He'd come in quietly with two coffees and a printout. "You'll want this. Ruth flagged it again. Separately."

Ruth had not trusted the register. Two months after raising R-117, when it was clear nothing was moving, she had written a short paper for the Digital Services steering group, the monthly meeting where Felix and his directors reviewed the programme. Kalu had found it in the meeting archive. It was one page, in the same plain register as everything else she wrote, and it ended with a single recommendation in bold:

***Document before modernise.** We should not use AI-assisted refactoring on Escalation patient-matching until its legacy behaviour is written down and tested. The failure mode is silent: results will appear delivered when they are not.*

"So the steering group saw it," Maya said.

"Not exactly." Kalu put the printout down in front of her. "This is what the steering group saw."

It was a single slide from the steering group pack for that month. *Programme risks: summary.* The slide had a small grey footnote: *Summary generated by Meridian Copilot from 19 submitted risk papers.* There were nine bullet points in tidy sentence case, each next to a small coloured dot. Most were green. Some were amber.

The seventh read:

*Minor technical risk identified in legacy module; no committee action required.*

The dot next to it was green.

Maya couldn't stop looking at it.

"That's her paper," she said.

"That's her paper." Kalu sat down opposite her. "The summariser went through nineteen risk papers that month and boiled them down to nine lines. Hers got that. *Legacy module*. It didn't say which. It didn't say patient matching. It didn't say silent failure, or results looking delivered when they weren't. It didn't say *catastrophic*. It said *minor*. I checked the minutes. The steering group spent forty minutes that day on the Assistant's expansion into Scotland and three minutes on the risks slide. Nobody asked about item seven."

"Did anyone read the original paper?"

"It was in the appendix of the pack." He paused. "The pack was a hundred and sixty pages."

Maya picked up the printout and held the slide next to Ruth's paper. The original was one page long and one sentence in it mattered. The summary was one line and contained none of what mattered. Something had read Ruth's warning carefully, understood its grammar, and turned it into a sentence that was true in every word and wrong in every way that counted.

She thought, absurdly, of a game she'd played as a child with her sister, passing a message along a line of cousins at a wedding. *Send reinforcements, we're going to advance* had arrived at the far end as *send three and fourpence, we're going to a dance.* It was the same thing. Here it had taken one step.

"Did Ruth ever see this?"

"I asked her. She did, afterwards. She raised it with Josh, who said it was a summarisation quirk, the original paper was still in the pack, and anybody who wanted the detail could read it." Kalu took his glasses off and polished them on his tie. "Which was true."

"Everything is true," Maya said. "That's the problem. Every single step of this is true."

---

She went back to King's Cross at four and found Ruth still at her desk, still upright, still writing.

"I read R-117," Maya said. "And the steering paper. And the slide."

Ruth put her pen down.

"I'm not angry about the slide," she said, after a moment. "People think I should be. I was, for a week. But it isn't malicious. It's a machine that's very good at making things sound reasonable, being asked to make nineteen things sound reasonable on one page. Of course it chose *minor*. Most risks are minor. It played the odds." She looked at her notebook. "What I'm angry about is that after the slide, after the register, after I asked about it in person three more times, the conclusion everybody came to was that I was the problem. I was *slowing things down*. Ruth wants two weeks of documentation before anyone's allowed to touch a module everybody agrees is a mess. Ruth won't use agents on patient-facing code. Ruth's from devices, Ruth doesn't get how software works now." Her voice stayed perfectly level. "Then they moved me to test tooling. Which I don't mind, actually, I'm quite good at it. But I understood what it meant."

"Why didn't you escalate further? Above Felix?"

Ruth looked at her, and for the first time something like fatigue showed through the composure.

"Ms Reyes, I raised it in the register, in a paper, at the steering group and in person. I did it in writing, with a specific named failure mode and a specific mitigation and an estimate. I have a fifteen-year-old daughter. When I go to bed at night I think about what I'd want someone to do if it were her bloods that went nowhere. I did everything I knew how to do, in exactly the way the organisation says you should do it." She paused. "What would you have done that I didn't?"

Maya didn't answer. She found she didn't have an answer that wasn't a lie, and she had a strong feeling that Ruth Okafor would know.
