---
status: accepted
date: 2026-08-23
---

# On-device agent, gateway-only backend

Toni's agent loop runs inside the iOS app and all user data (projects,
tasks, notes, chat history) stays on the device; the backend is an LLM
gateway only — it holds the model API key, enforces per-tier rate
limits chunked through the day, routes cheap tasks to cheap models and
logs spend. Two facts force this shape: the tools the agent calls
(EventKit calendar and reminders, the timer, the user-owned notes
folder) only exist on the phone, so the loop must run there; and the
"LLM spend never exceeds the tier price" constraint needs a server-side
key and limiter, so a no-backend app was out.

## Considered options

- **No backend** — key ships in the app, no place to enforce spend
  limits; would be rebuilt before any second user. Rejected.
- **Full backend** — data and agent server-side; contradicts the
  local, user-owned notes decision and can't book the user's calendar.
  Rejected.

## Consequences

- No multi-device and no web chat without adding a sync layer later;
  accepted as a non-goal of the kickoff push.
- The gateway is stateless with respect to user content; it sees
  prompts in transit, stores nothing of them.
