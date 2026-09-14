# Chapter 1 — The Flag That Didn't Fire

*Draft — first pass, rewritten 2026-09-11. Presented as incident artifacts rather than a narrated scene, deliberately: the book is single-POV on Maya (see `writing-plan.md` §4b), and she isn't in the building yet when this happens. Documents let the cold open land without breaking that rule — and it's the first of many documents this story doesn't trust at face value. Rewritten to fix a conceptual error in the first draft: the incident must not be a failure inside Meridian's AI **product** (the patient-facing chat interface Felix champions) — it needs to be an ordinary, unglamorous piece of internal software, whose recent modification with AI **coding tools** is what the investigation exists to uncover. See the scope note in `writing-plan.md` §1.*

---

**MERIDIAN HEALTH GROUP — CLINICAL SAFETY**
**Serious Incident Report: Reference SI-2607**
**Subject: Delayed Escalation of a Critical Pathology Result**
**Classification: SEV-1. Distribution: Executive, Clinical Safety, Legal.**

---

**Day 0, 08:14** — Routine blood panel result received via the pathology lab feed for Patient A (M, 61, known chronic kidney disease stage 4, existing risk marker for hyperkalaemia). Potassium: **7.2 mmol/L** (critical; normal reference range 3.5–5.0).

**Day 0, 08:14:02** — Result processed by the Critical Results Escalation service ("Escalation"). No alert generated. Result filed to the patient's record as routine, alongside eleven other results received in the same batch.

**Day 0–8** — No clinical contact initiated regarding the result. Patient not informed his bloods were abnormal.

**Day 9, 14:20** — Patient presents to Meridian General A&E by ambulance with palpitations, muscle weakness, and cardiac arrhythmia.

**Day 9, 14:52** — Repeat potassium: 7.8 mmol/L. Emergency treatment initiated.

**Day 9, 16:10** — Patient stabilised. Admitted to the Coronary Care Unit for monitoring.

**Day 9, 19:00** — Attending consultant reviews the patient's recent history ahead of a ward round and finds the Day 0 result on file, unactioned, with no record of any escalation. Flags to Clinical Safety the same evening.

**Day 10, 07:30** — Clinical Safety confirms: given the patient's existing risk marker, Escalation should have generated an URGENT alert to his GP and consultant on Day 0. It did not.

**Day 10, 09:00** — Digital Services confirms Escalation's patient-matching logic was modified six weeks prior, as part of a long-deferred refactor of the identity-matching code linking the pathology feed to Meridian's clinical risk-flag records. Root cause investigation opens.

**Day 10, 11:00** — CQC notified per Meridian's Serious Incident Framework.

**Day 10, 14:00** — Group CEO convenes an emergency executive session. Item 1: an external investigation, independent of Digital Services leadership. Item 2: the line to take.

**Day 10, 15:40** — Patient's condition stable. Expected to make a full recovery.

---

*Attached: Escalation service architecture note (last substantively revised four years before the Day-0 refactor), pathology feed integration specification (v2, undated), identity-matching logic pull request #4471 ("Simplify legacy patient-matching — remove dead code paths").*
