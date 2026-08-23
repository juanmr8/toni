# Triage Labels

The skills speak in five canonical triage roles. In this repo each
role maps to a Linear label with the same string (create the label on
first use if it doesn't exist yet):

- `needs-triage` — maintainer needs to evaluate this issue
- `needs-info` — waiting on reporter for more information
- `ready-for-agent` — fully specified, ready for an AFK agent
- `ready-for-human` — requires human implementation
- `wontfix` — will not be actioned

When a skill mentions a role (e.g. "apply the AFK-ready triage
label"), apply the matching Linear label.
