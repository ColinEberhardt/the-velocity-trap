# Chapter 2 — The Fixer

Maya Reyes was halfway through telling Priya why her report was too long when her phone rang.

"It isn't that it's wrong," she was saying. They were in the small glass room on the third floor of Kestrel Advisory's offices in Farringdon, the one with the whiteboard nobody could ever quite clean. Priya's draft lay on the table between them, forty-one pages, with Maya's pencil all over the first twelve. "It's that it's honest in every direction at once. You've found six contributing factors and given them all the same weight. The client is going to read this and do nothing, because you've told them everything matters equally, and when everything matters equally it means nothing does."

"But they did all contribute," Priya said. She was three years into the firm, sharp and stubborn in a way Maya liked and occasionally found exhausting. "If I cut four of them, I'm just picking."

"You're always picking. The question is whether you're picking on purpose." Maya's phone buzzed against the table. It was Graham, the managing partner, who never rang when an email would do. "Sorry. One minute."

She took it in the corridor.

"Are you free?" Graham said.

"I'm with Priya."

"Be not with Priya. Meridian Health Group. Their CEO wants you in Paddington by two. They had a serious incident at one of their hospitals on Monday night and she wants it understood before anyone else understands it for her." He paused. "Her words, roughly."

"What kind of incident?"

"A patient nearly died. A blood result didn't get to the doctor. They think it's a systems failure. It was on the BBC website an hour ago, and the BBC thinks it's their chatbot."

"Is it?"

"Nobody knows. That's why they want you."

Maya looked back through the glass at Priya, who was rereading her own page nine with her lips moving slightly. Maya thought, unbidden, of how she must look from the other side of that glass: forty-four, neat, her glasses pushed up into her hair. A woman who made other people's messes go away for a living.

"I'll be there at two," she said.

---

Meridian's head office was a tall pale building near Paddington Basin, the kind designed to look like a hospital without anyone ever having to be ill in it. In the lobby a screen ran a loop of smiling clinicians and the words MERIDIAN ASSISTANT — CARE THAT LISTENS. A security guard escorted Maya to the twelfth floor, where Deborah Ashworth's assistant met her and walked her to a boardroom with a view across west London to the rain.

Ashworth stood when she came in. She was in her early fifties, dark-suited, with the kind of stillness Maya associated with people who had been on television enough times to stop moving their hands. There were two men at the table. One was introduced as Robert Kalu, the Group's general counsel: grey at the temples, reading glasses on a cord, a legal pad covered in tiny handwriting. The other was the Medical Director, who stayed for ten minutes and spent most of them describing, carefully and without adjectives, what had happened to Desmond Hale.

When he left, Ashworth folded her hands on the table.

"Thank you for coming at short notice, Ms Reyes. I'll be direct. On Monday night, a critical blood result for a patient at our Kingsgate hospital was not escalated to the clinical team. The patient suffered a cardiac arrest. He survived and he is stable. We have notified the regulator. We have opened a serious incident investigation, as we're required to, and that investigation will take the time it takes." She paused. "I don't have the time it takes."

"Why not?"

It was a slightly impertinent question and Maya saw Kalu's pen stop. Ashworth didn't seem to mind.

"Because the board meets a fortnight on Friday," she said. "Because the regulator will want to know, before then, whether this can happen again, and I'd like to be able to tell them. Because this morning a journalist at the *Guardian* asked our press office whether Meridian's AI assistant had 'lost' a patient's blood test, and by this evening every outlet in the country will be running it, whether or not it's true."

"Is it true?"

"No." Ashworth said it with real force, the first unguarded thing she'd said. "The Assistant is a patient-facing chat service. It helps people book appointments and understand their discharge letters. It doesn't touch lab results. It has nothing to do with this. And I'm going to spend the rest of the week explaining that to people who have already decided otherwise, because 'AI chatbot nearly kills pensioner' is a better headline than whatever this actually is." She took a breath. "So I need to know what this actually is."

Maya took her glasses out of her hair and put them on the table, which she did when she wanted to think without looking like it.

"What do you know so far?"

Kalu answered. "The result came from the lab normally. The system that's meant to route critical results to the right doctor is called the Critical Results Escalation service. Internally they just call it Escalation. It's about ten years old. It received the result and decided there was nowhere to send it, so it sent it to an outpatient clinic's inbox in Watford, which was closed. Our engineering team believe it's linked to a recent change to the code. They're being careful about saying more than that."

"Careful in the sense of uncertain, or careful in the sense of frightened?"

Kalu almost smiled. "Both, I'd think."

"Who made the change?"

The room went still. Maya noticed it and filed it. It was the stillness of a question everyone had already asked, privately, and nobody wanted to be seen asking first.

"A member of the engineering team," Ashworth said evenly. "We have a name. I'm not going to give it to you yet. I don't want you anchored."

"That's sensible."

"I'm a sensible person." Ashworth's eyes didn't leave her. "Here is what I'd like from you, Ms Reyes. Your firm has a reputation for this. Your managing partner tells me you've done eleven of these and that the clients were happy with every one. I'd like a clear, independent account of what went wrong and why, delivered to me before the board meets. And I'd like it to tell me whether this was the act of one person, or a failure we should expect to happen again. Because those are two very different conversations with the regulator."

Maya heard what was underneath the second sentence. In her experience it was nearly always there. Ashworth wasn't asking her to name anyone. She was letting Maya know which answer would be easier to live with.

Maya could see the shape of that report from here. *A change to a legacy system was made by an individual without adequate understanding of its dependencies. Review controls were not applied with sufficient rigour. Recommendations: strengthen change control for safety-critical services; mandatory additional training.* She could write it in her sleep. She had written versions of it eleven times, and every one had been closed, filed, paid for and thanked.

"I'll tell you what I find," she said.

"That's all I'm asking."

It wasn't, but Maya let it pass.

---

Ashworth left to take a call from the chair. Kalu stayed and walked Maya to the lifts, which she took as a signal. They stood by the window while the lift indicator crawled up from the lobby.

"Can I say something off the record?" he said.

"I'm a consultant, Mr Kalu. Nothing's on the record until I write it down."

"Robert, please." He looked out at the rain. "I've been at Meridian six years. Before that I spent fifteen years defending NHS trusts in clinical negligence cases. I've read a lot of incident reports." He paused. "I don't think this is a person."

"You've seen something?"

"I've seen the way the engineers talk about it. Nobody's defensive. They're confused. When one person's made a mistake, everyone around them is defensive, because they're working out how close they were to it. These people aren't working out how close they were. They're working out how it was even possible." The lift arrived and its doors opened, and he held one with his hand. "The board will want a name. I'll want a name too, in about a week, because a name is legally much tidier. A person is easier to fire than a system. But if it's the system, and we fire a person, it happens again, and next time I'm explaining to a coroner why we knew."

Maya looked at him for a moment.

"Why are you telling me this?"

"Because Deborah's a very good chief executive under a great deal of pressure, and you're the person she hired to make the pressure go away." He let go of the door. "I'd like you to be slightly worse at that than usual."

---

She rang Priya from the taxi.

"Did you get it?" Priya said. "The Meridian thing? It's everywhere. Twitter thinks the chatbot did it."

"It wasn't the chatbot."

"How do you know?"

Maya opened her mouth and found she didn't have a good answer. Ashworth had told her so. She'd believed it, because Ashworth was right that it was the kind of story the press would want, and Maya disliked the press. That wasn't knowing. She was tired, and it annoyed her that a junior had caught it.

"I don't yet," she said. "Good question. Listen, I need you to pull everything public about Meridian's digital estate. Annual reports, conference talks, job adverts. Anything their engineers have said on podcasts. I want to know how they say they build software before I see how they actually do."

"On it." A pause. "Maya? About my report."

"Cut it to two factors and put the other four in an appendix."

"But—"

"Priya, I'm about to spend two weeks working out which of a dozen reasons a man nearly died. When I'm done I'll have to tell a board which one matters. Practice picking."

She hung up and looked out at the wet streets going by. On a bus shelter on Edgware Road there was a poster for the Meridian Assistant, a woman holding a phone and smiling at it. CARE THAT LISTENS.

Somebody had spray-painted a question mark after the word LISTENS.
