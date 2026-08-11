# homelab-control-mcp (sanitized mirror)

> **Original:** private. This is a redacted overview — no secrets, IPs, or internal hostnames.

## What it is
A **Model Context Protocol (MCP) server** that exposes controlled homelab operations to AI agents.
Agents call tools over stdio JSON-RPC; the server maps them to safe, audited local actions.

## Verified structure (redacted)
```
homelab-control-mcp/
├── .superpowers/            # planning + SDD reports (engineering log)
├── .venv/                   # python venv (excluded from public)
├── src/                     # server + tool definitions
├── tests/                   # tool/permission tests
├── pyproject.toml
└── README (this file)
```
~4,700 files total in the private copy (mostly `.venv`, caches, assets). **Only structure + design are mirrored here.**

## Design (what was built)
- **Tool registration pattern** — each homelab capability is a typed MCP tool with an input schema.
- **Permission gating** — tools are classified by risk; destructive ones require explicit confirmation.
- **Agent-safe surface** — agents never get a shell; they get curated, validated operations.
- **Local-first** — bound to localhost; no inbound network exposure.

## Sanitized
- All service names, host addresses, and auth config removed.
- `.env` / credentials: not present in this mirror (templates only, placeholder values).
- Internal hostnames (e.g. `zserverai`, `zghost`): removed.

## Why it matters
Proof of building the **agent↔system integration layer** — the same pattern an AI product uses to
let its agent safely act on backend systems (exactly what a visa-automation agent needs).
