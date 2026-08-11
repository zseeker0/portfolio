# hermes-command-center (sanitized mirror)

> **Original:** private. Redacted overview — structure + design only. No secrets, IPs, or paths.

## What it is
An **agent orchestration dashboard**: a backend API + frontend that visualizes running AI agents,
services, and projects in real time, and exposes their status over HTTP.

## Verified structure (redacted)
```
hermes-command-center/
├── dashboard-api/           # Node/Express status API (.env.example only)
│   └── src/server.js
├── frontend/                # Vite/React dashboard
│   ├── public/assets/       # canvas world art (MIT Pixel Agents assets)
│   └── index.html
├── docs/superpowers/        # specs + plans (agent-world design, art bible)
└── .gitignore
```
~5,100 files in private copy (mostly `node_modules` + art assets). **Mirror shows design only.**

## Design (what was built)
- **Status API** (`/api/status`) aggregates: agents, services, endpoints, project state, token usage.
- **Real-time polling** — frontend polls every 15s; agent state drives UI (working / online / idle).
- **Canvas world** — HTML5 Canvas 2D, 60fps loop, depth-sorted scene, multi-room layout.
- **Project characters** — each project becomes a canvas character; status-routed seating
  (active → office, failing → boardroom, planned → overflow).
- **Camera presets** — overview / per-zone zoom + drag-to-pan + click-to-follow (LERP).

## Sanitized
- `.env` values, internal URLs, DB paths: removed (`.env.example` templates only).
- Real project names / slugs: replaced with generic counts (e.g. "27 projects").
- Art assets: MIT-licensed third-party; attribution retained, binaries not redistributed here.

## Why it matters
Shows I can build **agent control planes + monitoring UIs** — the ops layer a small AI team needs
to see what its agents are doing.
