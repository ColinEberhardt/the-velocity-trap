# Chapter 1 — 23:47

```
2026-02-23 23:47:02.114  INFO  lab-ingest   Result received  accession=KG-2602-88341  test=K+  value=7.2 mmol/L  flag=CRITICAL
2026-02-23 23:47:02.131  INFO  escalation   Critical threshold breached  rule=POTASSIUM_HIGH  patientRef=MRN-2208513
```

Ward 4B at Meridian Kingsgate Hospital went quiet after eleven. It never went silent, though. Bays creaked, a drip pump on the far side gave its soft two-note complaint every so often, and somebody's daughter was still murmuring on the phone in the corridor long after she should have gone home. Helen Marsh liked that hour. The day's admissions had settled, the evening drugs round was done, and for a little while the ward was hers.

She was writing up notes at the station when Kofi came back from bay three with an armful of linen and a face that said Mrs Adebayo had asked again whether anyone had found her glasses.

"They're in her slipper," Helen said, without looking up.

"How do you know that?"

"Because they were in her slipper last night."

Kofi laughed and went to check. Helen finished her note on the hip in bed eleven, Mr Hale, two days post-op and doing well. Seventy-one, a retired bus driver from Harrow, with a sense of humour he had clearly been using on passengers for forty years. He'd told her at nine o'clock that the hospital food was better than his late wife's cooking and that she should on no account repeat this to anyone. His evening obs were unremarkable. His bloods had gone down to the lab at eight with the rest of the post-op bay, the way they always did.

```
2026-02-23 23:47:02.140  INFO  escalation   Resolving patient  patientRef=MRN-2208513
2026-02-23 23:47:02.162  WARN  escalation   No active encounter found for patientRef=MRN-2208513
2026-02-23 23:47:02.163  INFO  escalation   Fallback routing  destination=INBOX:WATFORD-PREOP
2026-02-23 23:47:02.171  INFO  escalation   Result status=DELIVERED
```

Down the corridor, in the on-call room above the mess, Dr Anjali Rao lay on top of the covers in her scrubs with her pager on her chest. She was the medical registrar for the surgical wards that night. That meant every deteriorating patient, every unexpected chest pain, every potassium that came back strange from the lab between now and eight o'clock was hers. On a bad night the pager went every twenty minutes. On a normal night it went every forty-five.

It didn't go.

She woke once, around one, and checked it the way people check a phone they think has died. Battery fine. Signal fine. She lay back down and thought, with the superstitious caution of every doctor who has ever been on call, that this was the kind of thing you didn't say out loud.

```
2026-02-24 00:02:02.000  INFO  escalation   Acknowledgement window check  accession=KG-2602-88341  status=DELIVERED  ack=NOT_REQUIRED
```

Fifteen minutes after a critical result was released, Escalation was supposed to check whether anyone had acknowledged it. If nobody had, it paged the next person up, and then the next. Most of the people who used it every day had never heard its name. To them it was simply the reason the pager went off. It had replaced the old way, where a biochemist rang the ward in the middle of the night and read out a number to whoever picked up. The phone calls had been unreliable. Wards didn't answer. Numbers got misheard. Escalation never misheard anything and never got tired. When it was introduced in 2019, the lab had stopped phoning.

Tonight Escalation had not been told that anyone needed to acknowledge anything. As far as it was concerned, the result had gone to the right inbox and the job was done.

Helen did her two o'clock round. Mr Hale was asleep on his back with his mouth open, snoring in a slow, wet rhythm that she noted and didn't worry about. Plenty of men his age snored like that. His pulse at midnight had been sixty-eight. She didn't wake him to take it again. You let post-op patients sleep if you could, because sleep was the one thing the hospital was worst at giving them.

At three, the daughter in the corridor finally left. At half past three, a man in bay two pulled out his cannula and bled on the floor, and Helen and Kofi spent forty minutes cleaning up, re-siting, reassuring, and filling in the incident form. At four, she ate half a cereal bar standing up.

```
2026-02-24 00:17:02.000  INFO  escalation   Escalation tier check  accession=KG-2602-88341  status=DELIVERED  tier=NONE
2026-02-24 04:00:00.000  INFO  results-inbox  Unread items  inbox=WATFORD-PREOP  count=1  (clinic hours 08:30–17:00)
```

At 05:41 Kofi went into bay four with the observations trolley. He knew straight away. Later, in the debrief, he struggled to explain how. Mr Hale's colour was wrong. It was grey instead of pale, and the snoring had gone. Kofi put two fingers to his wrist and counted, and counted again, because the number didn't make sense. Thirty-four. Irregular. Then there was a long gap, long enough for Kofi to say "Mr Hale? Desmond?" loudly, and then another beat.

He hit the emergency buzzer.

Helen was there in eight seconds. She had done this enough times to have no memory afterwards of deciding anything. She pulled the curtain back, dropped the head of the bed, checked for breathing and a carotid pulse, felt one, faint and slow, and then didn't feel it. She said "Call it," and Kofi was already on the phone saying *cardiac arrest, Ward 4B, bay four* in the flat voice they trained you to use. She put the heel of her hand on Mr Hale's sternum and started counting.

Dr Rao heard the crash call over the speaker in the on-call room. She was down two flights of stairs before she fully understood it was on her ward. She arrived to find Helen on her third cycle of compressions and the defibrillator pads already on, and she did what you do. Rhythm check. The trace on the screen was broad, slow and ugly.

"What are his bloods?" she said.

Someone pulled them up on the ward computer. It took longer than it should have, because the result wasn't attached to his admission and they had to search for it. When it came up, the student nurse who found it read it aloud and then read it again, as if she hadn't understood her own voice.

"Potassium seven point two. Resulted at eleven forty-seven last night."

There was a short silence in the bay. It lasted maybe a second and a half, and nobody who was there ever forgot it. Everyone understood at the same moment that the number had been sitting somewhere for six hours.

Then Dr Rao said "Calcium gluconate, ten mils, now. Insulin dextrose. Get me a salbutamol neb," and the silence closed over and they worked.

They got him back on the second shock. He went to intensive care at 06:20 with a pulse, a blood pressure and a breathing tube, and a potassium that came down over the next four hours under drugs that should have been given before midnight.

```
2026-02-24 06:58:13.402  INFO  results-inbox  Item viewed  inbox=WATFORD-PREOP  user=system.audit
2026-02-24 06:58:40.117  INFO  escalation   Manual query  accession=KG-2602-88341  by=a.rao
```

At seven o'clock, after handover, Anjali Rao sat in the empty doctors' office on the surgical floor and tried to work out what had happened. She was thirty-three and had been a doctor for nine years. In that time she had seen a lot of things go wrong. She had seen bloods lost, bloods mislabelled and bloods sent to the wrong ward. She had once watched a junior colleague miss a critical sodium because he'd been paged eleven times in an hour and couldn't keep up.

She had never seen a critical result go nowhere.

She looked at the screen. The result was there, correct, flagged in red: CRITICAL, K+ 7.2. Its status said DELIVERED. Delivered to a pre-operative assessment clinic in Watford that opened at half past eight in the morning and had no idea Desmond Hale was in hospital.

She clicked through to the patient reference on the sample. It was a different number from the one on his wristband. When she searched for that number, the record came back with a small grey banner across the top: *This record has been merged. See MRN-2208510.*

She sat back in the chair and pressed her hands against her eyes.

The pager on her hip was quiet. It had been quiet all night, and she had been grateful.

---

By eight thirty, the incident had a number. By nine, the Director of Nursing had been told, and the Medical Director, and the Chief Operating Officer, and by ten someone in the Group's head office had put "Kingsgate — Serious Incident — Critical Result Not Escalated" into the subject line of an email with nine names on it. Somebody else replied all to say that the regulator would need to be notified within the day.

Mr Hale's son arrived from Milton Keynes at eleven. He sat beside the bed in intensive care and held his father's hand. A consultant he had never met, kind and very tired, explained that his father was stable, that the next forty-eight hours mattered, and that the hospital had already begun an investigation into why a blood result had not reached the team looking after him. The son asked the obvious question, the one the Group's lawyers would spend the next three weeks hoping nobody would ask in public.

"Was it a person or a computer?"

The consultant opened her mouth, and closed it, and said that they didn't know yet.

On the fourth floor of Meridian's head office near Paddington, a press officer was already drafting a holding statement. Her first draft referred to "a technical issue affecting one of our digital services." Her second draft took out the word *digital*, because the previous autumn Meridian had launched an AI-powered patient assistant with a great deal of fanfare. Everybody in the press office could see the headline that word would produce.

Nobody in the building, at that point, could have told you what the Critical Results Escalation service was, who owned it, or when anyone had last changed it.

```
2026-02-24 11:32:55.880  INFO  deploy-audit  Last change to escalation/patient-matching  PR=#4471  merged=2026-01-12  author=s.ilyas  approvals=1
```

In fact, someone had changed it six weeks earlier, on a Monday afternoon, in a pull request that took four minutes to approve.
