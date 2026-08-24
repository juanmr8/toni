# CONTEXT.md — domain model

The shared vocabulary for Toni. When a term here and casual usage
disagree, this file wins. Seeded from the kickoff grill (2026-08-23);
working notes in `~/vault/vault/products/toni/kickoff-grill.md`.

## Vocabulary

- **Toni** — a personal secretary for your life, not your job. Work is
  explicitly out of scope; that refusal is the positioning.
- **Opinionated about process, agnostic about content** — Toni's
  stance. Three structural opinions: everything has a next step, time
  exists on the calendar or it doesn't exist, progress gets logged.
  Zero opinions about what the user's free time is for.
- **First project** — the suggested onboarding journey: one thing the
  user always wanted to do, chosen (or discovered through an interview
  on values, available time, interests) at first run. The interview
  speaks natural language, with small multi-select fallbacks when the
  user doesn't know; it ends with candidate practices to choose from.
  Onboarding is over when the first block and the weekly check-in
  slot exist on the calendar. It showcases the
  product, earns trust, and calibrates how Toni works around this
  user. Skippable: the alternative onboarding shapes preferences
  directly (how to be asked, best catch-up times, reminder frequency).
- **Minimal sustainable version** — what shaping a project aims at:
  the smallest form of the ambition the user can sustain over time,
  translated into steps with deadlines.
- **Graduation** — a project's endpoint. Not "quest complete": the
  project becomes a **practice** — a standing part of the user's life
  with its notes, its rhythm, its weekly block. Graduation opens the
  "add a second thing?" door. Progress is visible, never scored; there
  is no game layer.
- **Block** — a time-blocked session on the user's real calendar,
  booked by Toni on confirmation. Carries a nudge at start, prep
  (notes, next step), and a close/log at the end. The log is
  free-form — told in text or voice, however the user wants;
  extracting structure is Toni's job. If no log comes, Toni asks —
  once, gently: no shame in a miss, no friction getting back.
- **Weekly check-in** — the heartbeat ritual, ~5 minutes at a slot
  set during onboarding: what happened, what didn't go as wanted,
  what to do about it next week — and how the practice is changing
  the user inwardly. Toni's role is perspective and questions (the
  railing), not judgment. Weekly by design: daily is too heavy,
  monthly loses the user. Not an end-of-project rite; sharing the
  reflection outward is a future door.
- **Quick-action** — a personal ask served from day one through the
  same chat + calendar + reminders plumbing ("remind me about the
  dentist Thursday"). The retention floor between blocks. Not a
  feature family: no email, no partner sharing, no dedicated
  life-admin surfaces in v1.
- **Borrow, don't build** — Toni's second principle, next to
  "opinionated about process". Calendar, reminders, timers, notes live
  in the apps already on the user's phone; Toni talks to them through
  their public interfaces rather than rebuilding them inside itself.
  The user never has to adopt a new place for their stuff.
- **Voice note** — the input primitive, alongside text: the user
  speaks, Toni keeps what was said (as text, attributed to the moment
  it was said) and acts on it like any message. Sending a voice note
  is the lowest-effort way to feed Toni, available from day one.
- **Task** — a piece of action that needs doing. Toni's own, closable
  by the user or by Toni (e.g. when a block's close says it got done).
  May belong to a project: a project's steps *are* its tasks. Shape,
  daily caps and ordering are discovered in use, not prescribed.
- **Reminder** — a time trigger, not work: "remind me about the
  dentist Thursday". Lives in the phone's Reminders app; Toni sets it
  and forgets it. Not a to-do list.
- **Calendar event** — time on the user's real calendar. A block is a
  calendar event Toni booked; a quick-action can also create one
  ("dinner with Ana Friday 8pm"). Time exists here or it doesn't.
- **Right tool for the thing** — tasks, reminders, calendar events and
  timers are four different things, each used only for its own case
  and never as a substitute for another. Corollary of Borrow, don't
  build.
- **Test cohort** — the handful of friends (≤5) living with the MVP
  alongside Juan during the kickoff push. Identified by an invite
  token, spend-capped per person, unpaid. A closed test group, not a
  free tier; it ends when paid tiers exist.
- **Note** — text Toni keeps on the user's behalf that the user would
  want to read years later: a recipe, what was learned in a block,
  the log of a project. A file the user owns and can open without
  Toni. Everything else Toni remembers is machinery, not a note.
- **Ideal week** — the slots where the user is genuinely free and
  willing to practice, declared at onboarding in natural language or
  by painting slots. The calendar knows what's booked; only the user
  knows which gaps are livable. Blocks are booked inside it.
- **Designed for failure** — Toni's third principle: missing a block
  is the expected case, not the exception. Recovery is one message,
  rearranging is cheap, checkpoints catch drift. No streaks, no
  guilt; progress is visible, never scored.
- **Chat session** — the chat opens clean every time; past sessions
  sit in a browsable history. The chat is an input source, not the
  relationship: continuity lives in Toni's memory (state, notes, the
  standing summary of the user), never in scrollback. Rituals render
  as structured cards inside a session.
- **The arc** — the adoption strategy: one project done very well →
  responsibility grows → a full personal secretary relied on for
  everything. The traditional-secretary capability set is the earned
  endgame, never the entry door.
