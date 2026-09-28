# Client Questions — PRD Follow-up

**For:** Week 5 client session — responses recorded after class
**Related:** [`PRD.md`](PRD.md) — each question below resolves one or more items marked
**(Assumption)** there.

These follow the guidance from the Week 4 narrative: ask about the past rather than the future,
ask for the exception rather than the normal case, do not ask the client to design the product,
and do not ask anything the material already answers. Each question is tied to a real detail in
the sample files so the client can answer from memory rather than speculate.

---

## Q1. The question that took too long

**Question:** What is the most recent question someone asked you about a past event that took
you a long time to answer? Who asked, and what did you have to dig through to find it?

**Why we are asking:** This tells us what search and analysis actually need to do, based on a
real request instead of a feature list. It also tells us who the users really are — if the
person asking was leadership, a sponsor, or a speaker, that changes the personas.

**Affects:** Goals G2, Personas, FR-13 through FR-16

**Client response:** Partial answer (paraphrased from my class notes, not her exact words). She has a couple of years of schedules from the previous person in her role, and it is too much data to work through. What she wants is to use it to find speakers and build the speaker list.

**What this tells us:** The slow question is not a one-off lookup. It is the recurring job of building each year's speaker list.

---

## Q2. Who counts as a speaker

**Question:** At the 2018 Richland course, David Anderson of Northwest Natural Gas spoke at a
sponsored dinner at The Reach Museum rather than in the classroom, and several days included
facility tours. When you have looked back at who has presented for the program, did people like
that count?

**Why we are asking:** The files mix classroom sessions with dinners, tours, receptions, and
logistics. We need to know which of those the client treats as part of the program's history
and which are just travel and meals.

**Affects:** FR-4, FR-15

**Client response:** Not covered in the Week 5 session — this question was not asked, or the answer was not captured in my notes. Carried forward in [`open-questions.md`](open-questions.md).

---

## Q3. The schedule versus what actually happened

**Question:** The files we have are marked "final," but think back to an event where the day
did not go as printed — a speaker swapped out, a session moved or ran long. When that happened,
did anyone go back and update the file?

**Why we are asking:** This decides whether the archive is a record of what was *planned* or
what *happened*. If the files were never corrected, the data will contain sessions that did not
take place, and we need to know whether the client wants a way to mark that.

**Affects:** Problem Statement, FR-8, FR-11

**Client response:** Not covered in the Week 5 session — this question was not asked, or the answer was not captured in my notes. Carried forward in [`open-questions.md`](open-questions.md).

---

## Q4. Shared sessions between programs

**Question:** The 2021 Energy Executive Course schedule notes that highlighted sessions included
Energy Executive Summit participants. The last time you needed to report on one program's
sessions, how did you handle the ones that were shared with another program?

**Why we are asking:** If a shared session is counted in both programs, counted in one, or
reported separately, the analysis numbers come out differently. We would rather learn how the
client has already been counting than invent a rule.

**Affects:** FR-5, FR-15

**Client response:** Not covered in the Week 5 session — this question was not asked, or the answer was not captured in my notes. Carried forward in [`open-questions.md`](open-questions.md).

---

## Q5. The last handoff

**Question:** Who has built these schedules over the past few years? When someone new took
over, how did they figure out where things were and how the previous events had been put
together?

**Why we are asking:** The product is handed off at the end of the semester, and the drift in
the files suggests past handoffs were difficult. Knowing how that went tells us what the
successor persona actually needs and how much technical skill we can assume.

**Affects:** Constraint C3, Goal G4, Successor persona

**Client response:** Answered (paraphrased from my class notes, not her exact words). She inherited a couple of years of schedules from her predecessor. When she needs a new guest speaker, it is usually someone her predecessor referred.

**What this tells us:** The handoff passed on files and a referral network, but not a usable speaker list. Much of the knowledge about who to invite still depends on the previous person.

---

## Q6. What you already know when you look someone up

**Question:** When you look up a past speaker, what do you usually already know about them —
their name, their company, the topic they covered, or roughly what year it was?

**Why we are asking:** My starting idea for the data is one row per talk, with the speaker, the
main topic, the session title, and the year. This question checks whether those are the right
columns without asking the client to design the database. Whatever she usually starts from is
what search has to work with, and anything she never knows up front does not need to be a search
field.

**Affects:** FR-2, FR-3, FR-13, FR-14

**Client response:** Not covered in the Week 5 session — this question was not asked, or the answer was not captured in my notes. Carried forward in [`open-questions.md`](open-questions.md).

---

## Q7. The tools already in use

**Question:** Right now, when you need to update a schedule, what program do you open, and who
else works on that file?

**Why we are asking:** A spreadsheet the staff already use every day could be easier to hand off
than a new tool. Before deciding anything like that, we need to know what the team is comfortable
with today and how many people edit the same files.

**Affects:** Constraint C3, Goal G4, Program Coordinator persona

**Client response:** Answered (paraphrased from my class notes, not her exact words). She prefers Excel or basic Office tools. Nothing complicated.

**What this tells us:** The product should fit into the tools the staff already use, so it can be handed off without training.


---

## Q8. How the speaker lineup gets built

*Added after class. This answer came up in the session and addresses the question I most wanted
to ask: how speakers and topics are chosen.*

**Question:** Think about the last event you planned. How did you pick the speakers and topics?

**Client response:** Answered (paraphrased from my class notes, not her exact words). Speakers are
decided by starting from last year's agenda and modifying it based on feedback. When a new guest
speaker is needed, it is usually someone referred by her predecessor.

She also said speaker quality is one of the most important factors, and that the Dean of CBE and the advisory board take part in decisions about speakers.

**What this tells us:** This is the core workflow the product supports. The starting point is
always the previous agenda, the filter is feedback, and new names come from referrals. That points
to three things the data needs: a link to the prior year's session, a feedback or status field, and
a record of who referred a speaker. Because the Dean and the advisory board are involved, the
information also has to be clear enough to share beyond the client.

**Affects:** Problem Statement, US-1, US-4, FR-2, FR-19 through FR-22
