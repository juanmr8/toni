# PRD — Toni kickoff: functional MVP in Juan's hands

Push: **Toni — kickoff** (Linear, initiative Toni). Drafted from the
kickoff grill (2026-08-23, decisions 1–11) and the PRD grill
(2026-08-23, decisions 12–19 + repo ADRs 0001–0002). Glossary:
repo `CONTEXT.md` — its terms win.

## Problem Statement

My free time disappears into defaults — social media, drift — instead
of the thing I always wanted to do. Work has an army of assistants
fighting for it; my life has none. I don't need more content or
another to-do app: I need someone opinionated about *process* —
everything has a next step, time exists on the calendar or it doesn't
exist, progress gets logged — and agnostic about *content*, who helps
me decide what my free time is for and then structures it, survives my
failures without shaming me, and remembers everything so I don't have
to.

## Solution

Toni: a chat-first personal secretary for your life, not your job —
an iOS app (Swift/SwiftUI) you talk to in text or voice notes. At
first run it suggests the first project: one thing you always wanted
to do, chosen directly or discovered through a short interview, shaped
into a minimal sustainable version (twice a week, tops) and booked as
blocks on your real calendar inside your ideal week. Toni preps each
block, takes your free-form log at the end, asks once — gently — when
a block passes silently, and runs a ~5-minute weekly check-in for
perspective. Between blocks it serves quick-actions (reminders,
calendar events, tasks, timers, questions, web lookups) through the
same chat. Notes are markdown files you own; continuity lives in
Toni's memory, not scrollback. The agent runs on-device against the
phone's own apps (Borrow, don't build); a thin provider-agnostic
gateway keeps LLM spend capped per user. Juan is user zero; a test
cohort of up to five friends joins via TestFlight with invite tokens.

## User Stories

### Onboarding — the first project

1. As a new user, I want Toni to open with a conversation, not a form, so that the product feels like a person from message one.
2. As a new user who knows my thing, I want to say it in natural language and skip straight to shaping, so that Toni never slows me down with questions I've already answered.
3. As a new user who doesn't know, I want a short interview on values, available time and interests — natural language with small multi-select fallbacks — so that Toni can propose candidate practices instead of asking me to invent one.
4. As a new user, I want to pick from a small set of proposed practices, so that choosing feels like recognition, not homework.
5. As a new user, I want to be asked for calendar permission at the moment Toni needs it to find my free time, so that the request is obviously justified.
6. As a new user, I want to declare my ideal week — when I'm genuinely free *and willing* — in natural language or by painting slots, so that blocks land where my life can actually hold them.
7. As a new user, I want Toni to propose a minimal sustainable version (twice a week, tops) with the first two or three tasks, so that I start with something I can sustain rather than an ambition that collapses.
8. As a new user, I want to adjust the proposal in chat and confirm, so that nothing lands on my calendar without my yes.
9. As a new user, I want onboarding to end with my first block and my weekly check-in slot on my real calendar and a project brief written to my notes, so that the first promise is concrete ("see you Tuesday at 19:00").

### Chat, voice, and memory

10. As a user, I want every app open to start a clean chat session, so that talking to Toni is frictionless and never means scrolling to the bottom of history.
11. As a user, I want past sessions in a browsable history, so that I can revisit earlier discussions.
12. As a user, I want to send a voice note and have Toni act on it like any message, so that feeding Toni is the lowest-effort act on my phone.
13. As a user, I want Toni to remember facts about me ("vegetarian", "never before 9am") and where my project stands, independent of any chat session, so that continuity lives in Toni, not in scrollback.
14. As a user, I want rituals (onboarding, block close, check-in) to render as structured cards inside the chat, so that recurring moments are recognizable at a glance.
15. As a user, I want Toni to refuse work topics gracefully, so that the "for your life, not your job" line holds.
16. As a user, I want Toni to say plainly when something is outside its verb list, so that I trust what it says it did.

### Blocks — the loop

17. As a user, I want a nudge notification when a block starts, so that the block exists in my attention, not just my calendar.
18. As a user, I want prep in that moment — my notes, my next task, anything Toni looked up — so that I start doing instead of remembering where I was.
19. As a user, I want to ask Toni to look something up on the web for a block ("three beginner videos before Tuesday"), so that prep has substance.
20. As a user, I want to close a block by telling Toni what happened, in text or voice, however I want, so that logging costs seconds and zero structure from me.
21. As a user, I want Toni to extract the structure from my free-form log (progress, notes to keep, tasks done or spawned), so that the record grows without my bookkeeping.
22. As a user who let a block pass silently, I want Toni to ask once, gently, with one-tap outs (move it / skip / actually did it), so that a miss costs one tap and no shame.
23. As a user, I want to rearrange blocks in one message ("move tonight to Saturday morning"), so that recovery is always cheaper than abandonment.
24. As a user, I want Toni to book blocks only inside my ideal week unless I say otherwise, so that structure respects my life.

### Quick-actions — the retention floor

25. As a user, I want "remind me about the dentist Thursday" to become a Reminder on my phone, set-and-forget, so that time-triggered memory costs one sentence.
26. As a user, I want "dinner with Ana Friday 8pm" to become a calendar event, so that Toni handles life admin, not just the project.
27. As a user, I want to create tasks in chat and have Toni or me close them, so that pieces of action have a home that isn't my head.
28. As a user, I want to see today's small set of tasks, so that a day has a shape without becoming a productivity system.
29. As a user, I want "set 50 minutes for cleaning" to start a timer visible on my lock screen, so that acting takes zero app-switching.
30. As a user, I want to ask Toni what my day or week looks like, so that the calendar has a conversational front door.
31. As a user, I want to ask Toni things it must look up on the web, so that my secretary can find answers, not just store mine.

### Notes — what I own

32. As a user, I want everything worth rereading in five years (project brief, logs, recipes, learnings) written as markdown files in a folder I can open with the Files app or Obsidian, so that my notes are mine, with or without Toni.
33. As a user, I want to ask Toni questions answered from my own notes, so that what I logged comes back when I need it.
34. As a user, I want deleting Toni to leave my notes intact on my device, so that trust never requires an export button.

### Weekly check-in — the heartbeat

35. As a user, I want a ~5-minute weekly check-in at the slot set during onboarding, so that reflection is a standing ritual, familiar from week one.
36. As a user, I want it to walk what happened, what didn't go as wanted, what to do next week — and how the practice is changing me inwardly, so that I get perspective, not a report card.
37. As a user, I want Toni to bring the week's evidence (logs, misses, closed tasks) into the check-in, so that reflection starts from what actually happened.
38. As a user, I want the check-in to end with next week's blocks confirmed or moved, so that reflection turns into booked time.
39. As a user, I want progress visible — the log, the growing practice — but never scored, so that there is no streak to lose.
40. As a user whose practice has become self-sustaining, I want the project to graduate into a practice rather than "complete", so that the endpoint is a standing part of my life, and the "add a second thing?" door opens.

### Test cohort and operations

41. As Juan, I want to onboard through the real flow with no dev shortcuts, so that I live exactly what a user lives.
42. As a friend in the test cohort, I want to install via TestFlight and paste an invite token once, so that joining takes a minute and no account.
43. As Juan, I want each token's daily LLM spend capped at the tier level, so that the cohort cannot cost me money.
44. As Juan, I want a spend log per user and per task type in the gateway, so that the cost model comes from data.
45. As Juan, I want to revoke a token, so that any cohort member can be cut off cleanly.
46. As Juan, I want to flip my own token to the premium model, so that I can feel the quality difference myself.

## Implementation Decisions

- **On-device agent, gateway-only backend** (ADR-0001). The agent
  loop runs in the iOS app, because its tools only exist there. All
  user data on-device. The backend is a thin gateway: holds provider
  keys, checks invite tokens, enforces per-user daily caps, routes
  task → model, logs spend, forwards streams. Stateless with respect
  to user content.
- **Gateway**: TypeScript on Vercel Functions, built on the Vercel
  AI SDK — provider-agnostic; the task→model routing table (chat /
  interview / check-in / background) is configuration. Launch config:
  cheaper tiers on Sonnet 5 (agent) + Haiku 4.5 (background jobs);
  premium tier on Opus 5. Prompt caching from day one (stable system
  prompt + tools first, volatile context after). Test cohort runs the
  Sonnet/Haiku config.
- **Auth**: invite tokens — one per person, generated by Juan, pasted
  once at first launch, sent as a bearer header. No accounts, no
  login screen. Revocable server-side.
- **Web search**: served through the provider's server-side search
  tool while on Anthropic; becomes a gateway-provided tool if the
  provider changes. Invisible to the app either way.
- **Storage** (ADR-0002): notes are markdown files in a `Toni/`
  folder under the app's Documents directory, exposed to the Files
  app. Machinery — projects, tasks, blocks, check-ins, chat sessions,
  preferences, the standing summary — is SwiftData records. Rule:
  readable-in-five-years → file; machinery → record. No sync, no
  iCloud feature in this push.
- **Capability contract (v1 verb list)** — the agent's tools, and the
  boundary of what Toni may claim it can do: calendar read
  (free/busy) and write (book/move/cancel blocks and one-off events)
  via EventKit; reminders create (set-and-forget) via EventKit;
  tasks create/close/list in Toni's store; notes write/append/read;
  timer start; memory update (standing summary, user facts); ritual
  runs (onboarding, block prep/close, weekly check-in,
  miss-recovery); local notifications (block nudge, unlogged-block
  follow-up, check-in prompt); web search. Everything else Toni
  declines by saying so.
- **Chat sessions**: open clean, history browsable. Per-turn model
  context is assembled — recent session messages + standing summary +
  today's state (blocks, open tasks) — never raw scrollback; keeps
  per-turn cost flat. Structured widgets (multi-select chips, slot
  grids, confirm cards, ritual cards) render inline in chat.
- **Voice notes**: on-device speech-to-text (Apple's speech APIs);
  transcript enters the chat as a normal message.
- **Timer**: in-app timer surfaced as a Live Activity (lock screen /
  Dynamic Island). The Clock app has no public timer API; Shortcut
  or AlarmKit routes may replace this later without contract change.
- **Notifications**: all local (scheduled on-device) — no push
  infrastructure in this push.
- **Rituals as deterministic state around the LLM**: onboarding,
  block lifecycle, miss-recovery and check-in are state machines
  whose conversational surface is the model but whose transitions and
  effects (book block, write brief, schedule follow-up) are code.
  Miss-recovery fires at most one follow-up per block.
- **Tasks**: single entity; a project's steps are its tasks (a task
  optionally belongs to a project). Shape, daily caps ("3 and 3"),
  ordering: discovered in use, deliberately unspecified here.
- **Graduation**: modeled as a project state with minimal UI; no
  ceremony built in this push.
- **Distribution**: TestFlight only; Juan + ≤5 friends.

## Testing Decisions

Good tests here assert **external behaviour at a seam** — effects and
contracts — never implementation details, and never the model's
judgment. Model calls in tests are scripted responses; CI is
deterministic and free. The model's actual quality (interview feel,
check-in tone) is evaluated by Juan and the cohort living with it.

- **Gateway contract seam** (highest): black-box tests against the
  running gateway with a fake provider — invite token accepted /
  rejected / revoked; daily cap enforced (n+1th request refused);
  task→model routing honored; streams and tool calls pass through
  intact; spend logged per user and task type.
- **Agent ↔ tool-surface seam**: the verb list is a protocol
  boundary; scenario tests drive whole rituals with scripted model
  responses against fakes (fake calendar, in-memory task store, fake
  clock, temp notes folder) and assert effects: onboarding ends →
  first block + check-in slot exist and the brief is written; block
  passes unlogged → exactly one follow-up scheduled; close says a
  task got done → that task is closed; miss-recovery "move it" →
  block rebooked inside the ideal week.
- **Persistence seam** (minimal): notes-file layout and record schema
  round-trip; deleting nothing on upgrade.

Prior art: none — the repo is newborn; these tests set the pattern.

## Out of Scope

Work/professional use of any kind (the refusal is the positioning) ·
email · messaging or sharing with other people · partner features ·
dedicated life-admin surfaces · Siri / App Intents / Shortcuts ·
the business-engine event diagram · native tool use beyond the timer ·
second project ("add a second thing" opens at graduation, later
push) · payments, tiers as billed reality, App Store, landing page,
demand probe (second push) · Android · any web client · sync /
multi-device / cloud storage of user data · gamification, scores,
streaks (progress visible, never scored — un-gamifying is
impossible, so none goes in) · plan-mode vs quick-ask chat split
(marked hesitation; prototype later) · Telegram or external chat
inputs · preferences-only onboarding route.

## Further Notes

- Pace (Juan): side project — better good to live with than fast.
- Push done evidence (grill decision 19): (1) Juan through the real
  first-project flow with two consecutive weekly check-ins on a real
  project; (2) the loop closed end-to-end once — interview → blocks →
  nudge → free-form log → that log surfaced in the check-in;
  (3) cohort onboarded via TestFlight + invite tokens, at least one
  friend through onboarding with zero verbal help; (4) spend log
  shows the cap enforcing and per-user run-rate under tier price.
  Explicitly not required: graduation reached, retention numbers,
  polish.
- Deliberately open, decided in build or in use: task shape and
  "3 and 3", timer mechanism, exact tier prices and rate-limit
  chunking design, production model per tier (Sonnet vs cheaper
  non-Anthropic challenger for entry).
- Source decisions: vault `products/toni/kickoff-grill.md` (1–19);
  repo `CONTEXT.md` (glossary), `docs/adr/0001`, `docs/adr/0002`,
  `docs/research.md` (open questions incl. iOS capability check).
