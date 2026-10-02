# Drafting notes — manuscript v2

A fresh second draft, written from `../resources/` only (the writing plan, characters, themes, source material). The v1 manuscript in `../manuscript/` was deliberately **not** read. The plan's §4b beat sheet sets the chapter structure, and v2 follows it exactly. The §5 drafting notes (the fixes Colin asked for during v1) are treated as requirements.

This file is the story bible for v2: the facts every chapter has to agree on.

## Form

- 24 chapters, close third person on Maya from chapter 2 onwards. Chapter 1 is a cold open seen from the night ward, with Escalation's own log lines cutting in, so it sits naturally in the site's monospace "incident report" layout.
- Past tense, British English, pounds sterling.
- Style: when it means the instructions that guide a coding agent, "Skill" is a capitalised noun ("the `legacy-simplify` Skill", "the internal Skills library"). Lower case is kept for human skill ("Which is a skill", "He wasn't missing a skill").
- Target ~45,000 words, at ~1,800–2,200 per chapter.

## The incident

- **Patient:** Mr Desmond Hale, 71, a retired bus driver. Admitted to **Meridian Kingsgate Hospital** (north-west London) for an elective hip replacement and on Ward 4B two days after surgery.
- **Duplicate record:** his pre-op assessment at a Meridian clinic in Watford was booked under "Des Hale", with a transposed date of birth. The two records were merged three weeks before admission. That retired the old ID, which now points at the surviving record in the master patient index (MPI).
- **The sample:** routine post-op bloods were ordered from the pre-op order set, so the sample label carried the **retired** patient ID.
- **The result:** potassium 7.2 mmol/L (critical), released by the lab at **23:47 Monday**.
- **The system:** the **Critical Results Escalation service** ("Escalation"). It was written in 2015 and is unglamorous Java that nobody outside engineering has heard of. In 2019 it replaced the lab's practice of phoning critical results to the ward. Its job is to resolve the patient to their active encounter, page the responsible clinician, expect acknowledgement within 15 minutes and escalate to the next tier at 30.
- **The bug:** an undocumented legacy method, `normaliseRef()` (2017), followed the MPI merge chain from a retired ID to the surviving record. Nothing in the code called it directly; it was invoked through a config-driven handler map (`handlers.yaml`), so static analysis showed it as dead. Six weeks before the incident, **PR #4471** ("Simplify legacy patient matching; remove dead code paths") was produced with an AI coding agent using the internal **`legacy-simplify`** Skill and shipped by Sam. It removed `normaliseRef()`. From then on, a result carrying a retired ID found "no active encounter" and went to the clinic's results inbox. That inbox is the Watford pre-op clinic's, closed overnight. Its status read **DELIVERED**.
- **Discovery:** at **05:41 Tuesday**, healthcare assistant **Kofi Mensah** found Mr Hale during obs with an irregular, slow pulse. He arrested and staff nurse **Helen Marsh** led until the crash team arrived. He was resuscitated, went to ICU and survived. On-call registrar **Dr Anjali Rao**'s pager stayed silent all night.
- **Why tests passed:** no test covered results arriving against a merged or retired ID.
- **Cost link (theme 2):** in Q2, after a bill spike, Josh's team was told to cut spend. The Skill was moved to a cheaper, smaller-context model tier ("economy tier"), so the agent never saw `handlers.yaml`.

## Clock (board deadline)

- Mon W1 night: the incident. Tue W1: incident declared and the regulator (CQC) notified.
- **Wed W1 (ch2):** Ashworth says the board meets "a fortnight on Friday" (Fri W3).
- Thu W1 (ch3–4), Fri W1 (ch5–6). Maya calls Marcus on Friday night. Sunday is Maya's call with her sister Lucia.
- **Mon W2 (ch7): 11 days.** Mon evening is the first visit to Shun (ch8). Tue W2 (ch9–10). **Wed W2 (ch11): 9 days.** Thu W2 (ch12–13).
- **Fri W2 (ch14–15):** the press runs the story, the regulator asks for preliminary findings early, and Ashworth brings the board forward to **Thursday W3**. That leaves **six days, not seven**.
- **Mon W3 (ch16):** an emergency full board. David demands a name; Ashworth holds them to Thursday (three days). Maya confesses to Marcus in the car park. Mon evening is the second visit to Shun (ch17).
- Tue W3 (ch18, Josh). Wed W3 (ch19, Sam). **Thu W3 (ch20, the board).**
- Act 4: the regulator gives Meridian 90 days to show remediation. Ch21 is ~5 weeks later, ch22 ~3 months later, ch23 in June (asparagus/broad-bean season), and ch24 the following winter.
- Season: the incident is in late February, so Act 1–3 nights are dark and wet.

## People

- **Maya Reyes:** senior consultant at **Kestrel Advisory**, ~44, trained as a mechanical engineer. She takes her glasses off to think, uses deflecting humour, calls her sister **Lucia** on Sundays and is amicably divorced. Her secret: eight years ago at **Halden Components**, a Midlands press shop, she named shift supervisor **Alan Pryce** in a clean report on a near-miss. Eighteen months later the same uninvestigated cause killed a setter at the sister plant in Telford. She tells Marcus in ch16 and puts it in writing for Priya in ch24.
- **Marcus Kwan:** late sixties, semi-retired. He wears a grey cardigan and an old waxed jacket. His line is "how do you know that?" and he demands benchmarks. Decades ago he sat on a review board that passed a system on the strength of its documentation, and it failed (kept as subtext). He investigated Aiko's old group.
- **Priya Shah:** Kestrel, three years in (ch2). Leading her first solo investigation in ch24.
- **Deborah Ashworth:** Group CEO from finance, who speaks in press-statement register. She calls Kalu "Bob" once.
- **Robert Kalu:** general counsel. In ch2: "I don't think this is a person… a person is easier to fire than a system."
- **Felix Adeyemi:** Chief Digital Officer, from product and a large consumer tech company. His father waited eleven hours in A&E with an unrecognised stroke, which is why he believes in the mission. He talks in outcomes. In ch10 he signed the AI tooling budget rise from **£1.1m to £3.4m a year** on velocity data alone ("PRs merged per engineer up 2.3×, cycle time down 41%"), with no risk section.
- **David Strand:** non-executive director, blunt. Not converted by the end, but no longer obstructing.
- **Josh Whitfield:** engineering lead, **Clinical Platform** (nine services including Escalation). Mortgage, two kids under six. Talks in metrics. He declined Ruth's request to be mandatory reviewer on patient-matching changes: "Let's revisit if we see actual issues." In ch18 he is revealed as the anonymised top spender (£4,180/month), running overnight agent loops.
- **Ruth Okafor:** senior engineer, Clinical Platform. Fifteen years in medical device firmware (infusion pumps), with a teenage daughter, **Temi** (15). Measured and meticulous. Her AI spend is flat at **£15/month**. She filed risk **R-117** eleven months before the incident; the "lightweight version" in the steering pack was flattened by an AI summariser to *"Minor technical risk identified in legacy module; no committee action required."* She has since been moved to test-harness work.
- **Sam Ilyas:** 24, 14 months at Meridian and one of the last graduate cohort hired. First in his family at university. He taught himself to code at 14 (a Pokémon damage calculator) and in the evenings writes a Game Boy emulator in C. He hedges and over-apologises. **His sentence (ch4):** "I read every line. I just never really know, with any of it, whether I actually know." Ch9 ends on: "I thought that was just what the job feels like now."
- **Callum Dyer:** the engineer who approved #4471 in four minutes.
- **Tariq Farouk:** platform engineer. He keeps a private dependency graph in which patient-matching logic is forked across **11 services**. He wrote the open-source **`sweep`** (refactoring instructions for coding agents) three years ago; its first rule is "Never assume code is dead because nothing calls it. Ask first." Meridian's internal fork of `legacy-simplify` was edited **8 times by 6 people over 14 months**, none of the edits benchmarked. `sweep` itself is drowning in AI slop PRs and has been cloned and relicensed. His **crack (ch11):** "Half the time I'm not sure I know what I know any more… ignore me." Software for one (ch23): a tiny tool for his father's allotment that says what to sow this week. 旬.
- **Aiko Sato:** chef-owner of **Shun**, an eight-seat counter in a mews in Clerkenwell. She used to run **Kaze**, four sites. A central prep kitchen changed a dressing recipe across all of them, the allergen sheet at one site wasn't updated, and a 19-year-old diner with a sesame allergy ended up in intensive care. Aiko had warned the expansion was outrunning the people. Marcus investigated, failed to protect her and lost that fight. She closed three sites.
- **Yuki:** Aiko's apprentice, two years in and not yet allowed to touch the tuna.
- **Helen Marsh:** the night staff nurse in ch1. In Act 4 she is seconded onto the pilot team as its clinical voice.

## Numbers to keep straight

PR #4471: −2,140 / +380 lines, approved in 4 minutes, AI-written description of 7 bullets with the risk in bullet 3 · spend gap 280 to 1 (£15 vs £4,180/month) · tooling budget £1.1m → £3.4m · 806-repo study, +15% velocity alongside worsening quality · 11 services · 8 edits / 6 people / 14 months · R-117 filed 11 months before · 19 risks on one slide · 340 pages of generated Escalation docs.

## Pilot team (Act 4)

Josh (lead, leading differently), Ruth (safety authority and sign-off), Sam and Helen Marsh (clinical). Tariq advises on the dependency graph. The pilot finds **four** merged records with unresolved critical flags elsewhere in the estate, which the old process would have missed.
- Ch7 addition: since 12 Jan, 14 critical results went to fallback; 3 were merged records — Mr Hale; a woman at Kingsgate (critical sodium, caught 4h late via repeat bloods); a man at Meridian Reading (critical haemoglobin, discharged, readmitted with a bleed). Before Jan the rate was zero. Josh adds a fallback-rate alert.

## Facts settled during drafting (after the continuity review)

- **Ruth's timeline:** R-117 filed 11 months before the incident. Steering paper about 2 months after that. Code-owners PR about 9 months before (declined by Josh). Performance review about 4 months after R-117 (rated *Partially meets*, no bonus), then moved to test tooling.
- **Tariq:** joined Meridian 6 years ago, when there were about 40 services. Wrote `sweep` at home 3 years ago. Meridian forked it about 18 months ago; the 8 edits span the last 14 months.
- **Aiko / Kaze:** the sesame incident was 30 years ago, when Marcus was 38. Aiko closed three sites the next year, sold the original Soho site a year after that, and opened Shun, which has had a waiting list for 28 years. Aiko is in her mid-sixties.
- **Halden:** the near-miss supervisor was Alan Pryce. The setter killed at the Telford plant 18 months later was Gary Holt.
- **Board (ch16, ch20):** chair Jonathan Pell; clinical NED Dr Fennimore (retired cardiologist); David Strand abstains on the rollout.
- **Regulator:** 90 days to evidence remediation (stated by Pell in ch20). Rollout approved comfortably ahead of that deadline, and the *FT* interview ran in late May.
- **Patient identity owner:** Sam. Josh leads the second team (observations / early-warning scores). Safety review has six people (Ruth asked for eight).
- **The *Guardian*'s "anonymous engineer":** a contractor who left in January (closed off in ch22).
- **Pilot catch (ch21):** the clinical-alerts service (one of Tariq's four). Four admitted patients had alerts stranded on retired records: 2 penicillin allergies, 1 anticoagulant flag, 1 malignant hyperthermia, the last at Meridian Reading and due for a knee replacement the next morning.
