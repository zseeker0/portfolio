# Portfolio — Sanitized Mirrors of Private Work

> Public, redacted overview of selected private repositories by Mohamed Hussien (@MohamedHussien-zseeker).
> Purpose: let recruiters / collaborators verify the *kind* and *scope* of work without exposing
> secrets, infrastructure, or proprietary code.

## What "sanitized" means here
Each project below is a **redacted mirror** — a faithful description of architecture, scope, and
engineering decisions, with all sensitive material removed:

- ❌ No `.env` values, API keys, tokens, or credentials (only `.env.example` templates, if any)
- ❌ No IP addresses, internal hostnames, or LAN ranges
- ❌ No absolute home/server paths (e.g. `/home/*`, internal domains)
- ❌ No SSH private keys or real SSH config
- ❌ No proprietary source for the one closed/commercial project (described at architecture level only)
- ✅ Public READMEs, file-tree structure, tech choices, and test counts are preserved
- ✅ Representative, scrubbed code snippets only where they teach the design

Private source remains private. This repo is a **portfolio**, not a leak.

## Projects covered
| Project | Type | Lang | What it shows |
|---|---|---|---|
| ContextLedger | AI-agent memory layer | Python | MCP server, FastAPI, SQLite FTS5, 93 tests |
| ai-dev-brain-kit | Local-first dev memory CLI | Python/Go | Self-contained binary, Obsidian graph, hooks |
| homelab-control-mcp | MCP server (agent↔system) | Python | Tool/server design, agent integration |
| hermes-command-center | Agent orchestration dashboard | TS/Node | Real-time agent monitoring, canvas UI |
| agent-command-center | Agent visualization dashboard | Python/JS | 27-project agent canvas, status routing |
| agent-os | Multi-agent orchestration | Python | Adapter pattern, agent/client/connection config |
| ai-dev-brain | Obsidian vault (dev brain) | HTML/MD | PARA knowledge structure |
| zserverai-infrastructure | Infra-as-code | Shell/YAML | systemd, docker, caddy, sanitized migration |
| helium-design-intelligence-saas | SaaS (proprietary) | TS/Py | Architecture only — no source |
| SaveSync / SaveSync-dev | Game-save backup tool | Python | Local-first backup/restore, checksum-verified |

See each folder for the per-project redacted README.

---
*Generated for outreach (Veeza AI). Verifiable, not exhaustive.*
