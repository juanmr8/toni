# Research — feeding the PRD

> **Note (Oct 2026):** partly outdated. The current architectural direction is in [`always-on-agent.md`](always-on-agent.md); read that first.

What we know, what we assume, and what still needs looking into
before/while the PRD hardens. Kickoff grill working notes:
`~/vault/vault/products/toni/kickoff-grill.md`.

## Market picture (from the kickoff grill, 2026-08-23)

- The work-assistant square metre is the most contested in software:
  platform owners (Google, Apple, OpenAI) plus funded startups
  (Motion, Reclaim, Martin, Dot). Toni does not enter it.
- The gap Toni claims: personal-only. A secretary for life outside
  work — appointments, partner logistics, and above all intentional
  free time. No platform roadmap targets it.
- The crisis the wedge answers: people default free time to social
  media instead of the thing they always wanted to do. Toni helps
  *decide* what free time is for, then structures it.
- Known risk (acknowledged, not resolved): B2C lifestyle-structure
  apps historically convert badly. The bet is the freshness of the
  twist; the demand probe (landing page stating the paid price) is
  the test, not this document.

## Open research questions

- Competitor scan for *personal-life* assistants specifically (not
  work productivity): who exists, how they died or survive, pricing.
- Pricing comps around the $15/mo anchor and a $5–8 entry tier.
- iOS capability check: EventKit (calendar + Reminders), App Intents
  (Siri/Shortcuts), on-device speech-to-text for voice notes
  (SFSpeechRecognizer / SpeechAnalyzer — default assumption:
  on-device, free), local user-owned notes storage. What the sandbox
  actually allows.
- Timer: the Clock app has no public API to start a timer. Candidate
  routes: in-app timer + Live Activity (v1 default), a user-installed
  Shortcut Toni triggers, AlarmKit (iOS 26+). Decide in build.
- LLM cost model per active user under the rate-limit chunking idea.
  The gateway routes per task through the Vercel AI SDK, so model
  choice is config. Decided tier → model: cheaper tiers on Sonnet 5
  (agent) + Haiku 4.5 (background), premium tier on Opus 5; prompt
  caching on. Rough cached cost: ~$0.010/turn Sonnet, ~$0.017/turn
  Opus → ~$6 / ~$10 per month at 20 turns/day. Open: actual turns/day
  from the cohort's spend log, and whether a non-Anthropic model
  beats Sonnet on secretary judgment for the entry tier.
- Free-time / screen-time stats worth citing on the landing page.
