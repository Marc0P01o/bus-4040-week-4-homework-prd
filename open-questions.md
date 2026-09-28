# Open Questions

Things the team PRD depends on that the Week 5 client session did not settle. Each entry has the
question, why it matters, and what we are assuming until it is answered.

Source: [`PRD-client-questions.md`](PRD-client-questions.md), updated after the Week 5 class.

---

## "It depends" and unclear answers

### OQ-1. Where does speaker feedback come from?

- **Question:** She said the lineup is modified based on feedback. What form is that feedback in —
  participant evaluations, her own judgment, comments from the advisory board — and where is it
  kept?
- **Why it matters:** Feedback is the filter that decides who comes back. None of the sample
  schedules contain it, so the product cannot filter on it unless we know where it lives.
- **Assumption for now:** Feedback is not in the schedule files. The product gets a Feedback and
  Status field that staff fill in by hand.

### OQ-2. How much history is actually in scope?

- **Question:** She described having a couple of years of schedules from her predecessor. The
  course material describes schedules from 2016 through 2026 across three programs. Which does she
  actually use, and does older history matter to her?
- **Why it matters:** It decides how much data has to be converted before the product is useful,
  and whether older speakers should be hidden by default.
- **Assumption for now:** Convert everything provided, but put the most recent years first and
  treat older records as history rather than candidates.

### OQ-3. How are referrals tracked?

- **Question:** New speakers usually come from her predecessor's referrals. Is any of that written
  down? What happens now that the predecessor is no longer the one making referrals?
- **Why it matters:** If referrals only live in one person's memory, the product could be the first
  place they are recorded. That may be as valuable as the historical schedules.
- **Assumption for now:** Add a "Referred by" field to each speaker. It starts mostly empty.

### OQ-4. Who has the final say on speakers?

- **Question:** She said the Dean of CBE and the advisory board take part in speaker decisions.
  Who approves the final list, and what does each of them need to see?
- **Why it matters:** If the Dean or the board reviews the list, the product has to present
  speaker quality in a way they can read quickly, not only in a way that works for the client.
- **Assumption for now:** The client builds the list, and the Dean and the advisory board review
  it. The speaker data includes quality information they can look at.

---

## Not covered in class — carried forward

These Week 4 questions were not asked or not captured. The team PRD keeps the Week 4 assumption
for each until someone gets an answer.

| # | Question | Assumption carried into the team PRD |
|---|---|---|
| Q2 | Do dinner and tour presenters count as speakers? | Keep them, labeled as non-classroom sessions |
| Q3 | Were files updated when the day did not go as printed? | Files show the plan, not what happened; staff can mark a no-show |
| Q4 | How are sessions shared between programs counted? | Record the session once and mark it as shared |
| Q6 | What does she already know when she looks someone up? | Search by name, organization, topic, and year |
