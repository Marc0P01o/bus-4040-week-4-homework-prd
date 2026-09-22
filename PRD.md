# Product Requirements Document — CBE Energy Program Schedule Archive

**Status:** Draft v0.1, written before the client interview
**Author:** Marc0P01o
**Last updated:** 2026-09-22
**Sources:** Week 4 narrative (client scenario), the 2021 EEC / Summit October schedule, and the 2018 Richland class agenda

> This is a first stake in the ground, not a final answer. Anything marked **(Assumption)**
> is a guess that needs to be confirmed or corrected with the client in Week 5. The questions
> meant to resolve those guesses are in [`PRD-client-questions.md`](PRD-client-questions.md).

---

## 1. Problem Statement

CBE runs executive education for the energy sector through three programs: the Energy
Executive Course, the Energy Executive Summit, and the Legislative Energy Horizon Institute.
Every event produces a schedule that records who spoke, on what, when, and where. Ten years of
those schedules, 2016 through 2026, exist only as documents built by hand by different people,
and the format drifted every time someone new made one.

The history exists, but it cannot be used. Answering a simple question — *has this person spoken
for us before? when did we last cover natural gas? which sessions were shared with Summit
participants?* — means opening files one at a time and reading. Building a new schedule starts
from a copied document rather than from what the programs have already done.

The two sample files show how far the formats have drifted:

- **Layout.** The 2021 schedule is a grid of days across and time slots down. The 2018 agenda is
  a list of times and descriptions, one table per day.
- **Times.** The same idea is written as `8:00-9:00`, `11:00-noon`, `11:00-Noon`, and
  `12:15-1:00pm`. The 2021 file states a time zone; the 2018 file does not.
- **Speakers.** 2021 gives a name in parentheses. 2018 gives name, title, and organization.
  Panels list several people plus a moderator, and one 2021 entry names speakers by last name
  only ("Cavanagh, Owens").
- **Meaning hidden in formatting.** The 2021 grid says highlighted sessions include Summit
  participants. The highlight color itself is data.
- **Mixed content.** Meals, buses, tours, hospitality suites, and check-in are interleaved with
  the actual sessions.

**Who has the problem:** the program staff who plan and run these events (the client), and
whoever inherits the programs after them.

## 2. Goals

Success means:

- **G1. One format.** Every schedule from 2016 through 2026 is in a single standard format, and
  nothing is lost silently — every session in a source file either appears in the organized data
  or is listed as excluded, with a reason.
- **G2. Fast answers.** Staff can answer a common question about past events — a person, a
  topic, a program, a year — in under a minute, without opening the original files.
- **G3. A head start on new events.** Staff can build a new event schedule starting from the
  organized history instead of from a copied document.
- **G4. Survives the handoff.** The client's team can keep the data current after the class
  ends, without needing a developer.
- **G5. Nothing is one mistake away from gone.** The data can be backed up and restored.

## 3. Constraints

- **C1.** The source data is the existing schedule files, 2016 through 2026, in inconsistent
  formats. The product has to work with that data as it is; the client will not re-create it.
- **C2.** All of the data is public, so there are no confidentiality requirements. It should
  still be handled with discretion.
- **C3.** The product is handed to the client at the end of the semester and must be usable and
  maintainable by non-technical staff. **(Assumption:** no dedicated IT support.)
- **C4.** It is built within one semester by a team of four using AI tools, and every change is
  reviewed through a pull request.
- **C5.** The original files are never modified. The organized data is a separate copy that can
  be traced back to its source.
- **C6.** Hosting, budget, and any university IT requirements are unknown. **(Assumption:** it
  must run without paid services.)

## 4. Target Users / Personas

**Program Director — primary user (the client).** Plans each event, invites speakers, and builds
the agenda. Knows the history well, but has to dig through files to confirm any of it.
*Needs:* fast lookup of past speakers and topics, and a starting point for new schedules.

**Program Coordinator. (Assumption)** Handles logistics — venues, buses, meals, hospitality —
and keeps the documents up to date. *Needs:* simple add, edit, and delete; confidence that an edit
will not break anything; a reliable backup.

**Program Leadership. (Assumption)** Oversees the three programs. *Needs:* a summary view of how
the programs have changed — topics over time, repeat speakers, organizations represented.

**Successor.** Whoever takes over a program later, with none of the history in their head.
*Needs:* data that explains itself, and a product that runs without the original student team.

## 5. User Stories

- **US-1.** As a program director, I want to look up a person and see every event they spoke at,
  with their session titles and the title and organization listed at the time, so that I can
  decide whether to invite them again.
- **US-2.** As a program director, I want to search sessions by topic word, such as "natural
  gas" or "regulation", so that I can see how often and how recently we have covered it.
- **US-3.** As a program director, I want to filter by program and year, so that I can compare
  the Course, the Summit, and the Institute.
- **US-4.** As a program director, I want to start a new schedule by pulling in past sessions and
  speakers, so that I am not rebuilding a Word document from scratch.
- **US-5.** As a coordinator, I want to add, correct, or remove a session or a speaker, so that
  the data stays accurate when plans change.
- **US-6.** As a coordinator, I want to see which source file a record came from, so that I can
  check it against the original when something looks wrong.
- **US-7.** As program leadership, I want summaries such as sessions per topic per year and the
  most frequent speakers, so that I can see how the programs have evolved.
- **US-8.** As a coordinator, I want to back up the data and restore it, so that a mistake or a
  lost laptop does not cost ten years of history.
- **US-9.** As a successor, I want every record to use the same format for dates, times, names,
  and programs, so that I can understand the data without knowing its history.

## 6. Functional Requirements

Each requirement is written so it can be tested. Grouped by the seven things the client asked for.

### 6.1 Organized data

- **FR-1.** Each event records its program, year, dates, and venue.
- **FR-2.** Each session records its event, date, start and end time, title, and the people
  involved with their role: speaker, panelist, moderator, or instructor.
- **FR-3.** Each person exists once. The title and organization shown at each appearance are
  stored with that appearance, not overwritten.
  *Test:* Roger Woodworth appears in the 2018 agenda as "Principal, Mindset Matters" and in the
  2021 schedule as both a speaker and a moderator. Looking him up returns all of those
  appearances under one person.
- **FR-4.** Sessions are kept distinct from non-session items (meals, travel, tours, receptions,
  hospitality). **(Assumption:** non-session items are kept and labeled, not discarded.)
- **FR-5.** A session shared with another program is recorded as shared.
  *Test:* the highlighted 2021 EEC sessions are marked as including Summit participants.
- **FR-6.** Every record links back to the source file it came from.

### 6.2 Standard format

- **FR-7.** All times are stored one way, with a.m. and p.m. resolved and the time zone recorded
  when the source gives one.
  *Test:* `11:00-noon` and `11:00-Noon` produce identical start and end times.
- **FR-8.** Converting a source file produces a report showing how many sessions were found,
  loaded, and flagged for review, with a reason for each flag.
  *Test:* for every file, found = loaded + flagged.
- **FR-9.** Ambiguous entries are flagged for a person to review instead of guessed. A partial
  name is only resolved automatically when it matches exactly one full name in the same event.
  *Test:* "Cavanagh, Owens" in 2021 resolves to Ralph Cavanagh and David Owens, who appear by full
  name earlier in the same schedule.
- **FR-10.** A session that continues after a break under the same title and presenter is
  recognized as one session. **(Assumption)**
  *Test:* Skip Collier's two 2018 blocks on July 7, before and after lunch, are treated as one
  session.

### 6.3 Add, edit, and delete

- **FR-11.** Users can add, edit, and delete events, sessions, and people without editing any
  file by hand.
- **FR-12.** Deleting asks for confirmation. Deleting a person who is attached to sessions shows
  which sessions would be affected before anything is removed.

### 6.4 Search

- **FR-13.** Users can search by person, words in a session title, organization, program, and
  year, alone or combined. Each result shows the event, date, session title, and people.
- **FR-14.** Partial names match.
  *Test:* searching "Woodworth" returns Roger Woodworth.

### 6.5 Analysis

- **FR-15.** The product shows counts of sessions by program and year, appearances per person,
  and sessions per organization.
- **FR-16.** Any search or analysis result can be exported to a spreadsheet-friendly file.
  **(Assumption)**

### 6.6 Backup and restore

- **FR-17.** One action creates a complete backup as a single file the user can store anywhere.
- **FR-18.** Restoring a backup returns the data exactly as it was.
  *Test:* back up, delete a session, restore — the session is back and every count matches the
  pre-backup numbers.

### 6.7 Build a new event schedule

- **FR-19.** Users can create a new event with a program, dates, and venue.
- **FR-20.** Users can fill the schedule by picking past sessions and speakers or by entering
  new ones.
- **FR-21.** The product flags sessions that overlap in time on the same day. **(Assumption:**
  events are single-track, as both samples are.)
- **FR-22.** A finished schedule can be produced as a readable document to share with
  participants.

## 7. Out of Scope

Deferred to a later release, or not part of this product:

- Participant registration, payments, or rosters
- Contacting speakers — invitations, contracts, honoraria
- Booking travel and logistics — hotels, buses, security badges
- Publishing schedules to a public website
- Automatically generating or recommending a schedule. The product helps a person build one; it
  does not build one for them
- Schedules before 2016, or from programs other than the three named
- Session content such as slides, recordings, or evaluations
