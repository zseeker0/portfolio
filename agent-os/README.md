# agent-os (sanitized mirror)

> **Original:** private. Redacted overview — architecture + adapter design only.

## What it is
A **multi-agent orchestration framework**: a thin core that wires different coding agents
(Codex, OpenCode, Hermes) into a unified agent/client/connection model, with CI.

## Verified structure
```
agent-os/
├── .github/workflows/ci.yml     # CI
├── adapters/                     # agent adapters (codex, opencode, hermes, base)
├── agent/agents.yaml
├── client/                       # client configs (codex, hermes, opencode)
├── connection/connections.yaml
├── identity/identity.yaml
├── lib/                          # backup, compiler, differ, manifest, validator, workflow
├── ACTIVATION.md
└── VERSION
```
82 files — small, focused framework.

## Design (what was built)
- **Adapter pattern** — each external agent is wrapped behind a common interface (`adapters/base.py`).
- **Declarative config** — agents, clients, connections, identity defined in YAML.
- **Factory pattern** — `factory_opencode.py`, `factory_skills.py` build adapters from config.
- **Safety lib** — `validator`, `differ`, `manifest`, `backup` guard changes before apply.
- **CI** — GitHub Actions runs the test/lint suite on every push.

## Sanitized
- No credentials, tokens, or real agent endpoints in this mirror.
- `identity.yaml` / `connections.yaml` values: described, not included.

## Why it matters
Demonstrates **orchestration engineering** — composing multiple AI agents behind one control model,
with validation/safety guards. Directly relevant to running agent fleets in production.
