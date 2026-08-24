---
status: accepted
date: 2026-08-23
---

# Notes are markdown files the user owns; state is app records

Notes (project notes, the progress log, anything the user would want
to read in five years) are plain markdown files in a `Toni/` folder
inside the app's Documents directory, exposed to the Files app so the
user, Obsidian, or iCloud Drive can open them and deleting Toni leaves
nothing hostage. Everything that is machinery — projects, tasks,
blocks, check-ins, chat history, preferences — lives in SwiftData
records. The rule for new data: readable-in-five-years → file;
machinery → record.

## Considered options

- **Everything in an app-private store with an export button** — the
  user would own an export, not their notes; contradicts the
  user-owned, Obsidian-like notes decision. Rejected.
- **A user-picked folder (security-scoped bookmark into iCloud Drive
  or an existing vault)** — most Obsidian-like, but permission and
  background-access edge cases bite early. Deferred: can be added
  later as a "move my folder" setting without changing the model.

## Consequences

- Two stores, two access paths; Toni's tools read/write notes as text
  and query state through SwiftData.
- No sync in this push (consistent with ADR-0001); iCloud Drive on
  the Documents folder is the user's choice, not Toni's feature.
