# Always-on agent: research notes

Current architectural direction for Toni (Oct 2026). Read this before `research.md`, which predates it and is partly outdated.

## Source
Stanford CS146S: "How always-on agents work", Lee Robinson (ex-Vercel/Cursor, now SpaceX), Oct 2026. https://www.youtube.com/watch?v=L1OBRtfPS34
Chapters: 2:35 How we got here, 6:13 What changed in the models, 10:06 Inside an always-on agent, 18:07 The harness, 27:26 Context engineering, 34:26 Where this is going.

## Main points
- Thick server, thin client. The agent loop runs as a durable workflow on Temporal, so a crash resumes mid-task instead of replaying from the start. The bot borrows a Firecracker VM that is snapshotted and put to sleep between jobs. State lives on the server; the VM is disposable.
- One tool bridges client and server: `send_to_user`. Each client (desktop, phone, Slack) only decides how to render what comes back.
- Proactive but polite: try the cheapest or most reliable option first before asking the user for input or approval. Wake sources include messages, Slack, calls and meetings, with a routing decision on whether to interrupt the user at all.
- Context engineering: tool search instead of every schema in the prompt, sub-agents so the main thread stays sparse, compaction while the prompt cache is warm, memory in three layers (core facts, dated logs, scratch notes that expire).
- Flywheel: daily bug -> eval -> fix harness/prompt -> ship; monthly new model trained on failures.

## Starters and references
- agileresearchservices/always-on-agent: Python, Anthropic SDK, Temporal. Prototype of the lecture's architecture (persistent, event-driven, memory/compaction/helpers). Not production-isolated.
- Open GrokBot (ishandutta2007/open-grokbot): self-hosted, BYO key, multi-agent, sandboxed tasks.
- OpenMausBot (milind-soni/OpenMausBot): bring-your-own-agent, local-first, runs on Claude/Codex/Grok CLIs, cloud desktop per bot.
- useAgent: AGPL, isolated Linux sandboxes per agent, Slack/GitHub/Gmail/Linear, approval steps, runs on an existing Claude Code subscription.
- GitHub topic `grok-bot-alternative`: 70+ more clones.
- Temporal cookbooks: model/tool/MCP calls as durable Activities; sandbox lifecycle routed through Activities (sdk-python 1.26.0).
- RyanAlberts/best-of-Agent-Harnesses: personal agent runtimes (OpenClaw, Hermes, Khoj, Agent Zero) and sandboxes (E2B, Daytona).

## Proposed stack for Toni
Temporal + Claude Agent SDK for the loop, a sandbox provider (E2B/Daytona/Firecracker) for the bot's computer, a single `send_to_user` tool, and a thin client (Telegram or Slack first, own UI later). Fastest demo: fork always-on-agent; fastest UI: fork OpenMausBot or useAgent.
