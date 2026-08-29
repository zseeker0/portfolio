# agent-command-center (sanitized mirror)

> **Original:** private. Redacted overview — design + UI architecture only. No secrets or paths included.

## What it is
A **canvas-based "Portfolio Office"** dashboard that visualizes AI agents and projects as
characters in a pixel world, with real-time status and camera follow. (Reuses MIT Pixel Agents art.)

## Design (from source README, v4.1)
- **Multi-room canvas** — 68×22 tile world, 16px tiles, 4 rooms + corridors.
- **60fps loop** via `requestAnimationFrame`; HTML5 Canvas 2D; depth-sorted scene.
- **Operational agent characters (3):** OpenCode, Codex, Flowise — each with desk + live state.
- **Project characters (27):** each project → deterministic character (hash of slug); status-routed
  seating (Live → office, Failing → boardroom, Planned → overflow).
- **Camera presets:** Overview / Office / Boardroom / Overflow + zoom 1–10× + drag-pan + follow.
- **Data sources:** `/api/status` (agents, services, endpoints, projects, token usage),
  `/api/agent/<name>`, `/api/project/<slug>`.
- **Tests:** backend (brain filtering, allowlist, 404, token, API), collision, portfolio composition.


