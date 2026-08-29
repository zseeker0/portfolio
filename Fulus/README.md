# Fulus (sanitized mirror)

> **Original:** private. This is a redacted overview — no secrets, IPs, or internal hostnames.

## What it is
A **multi-tenant cash/wallet ledger SaaS** for small Egyptian mobile shops (cash-in / cash-out "transfer" shops). Owners track two money flows — cash-in/cash-out money services and product sales — in one local-first, offline-capable system with daily reconciliation. Built as an operating pilot for a single pilot shop.

## Verified structure (redacted)
```text
fulus/
├── project-plan.md              # system plan / v1 spec
├── research/                    # research, competitive teardown, integration studies
├── phase1/                      # runnable pilot backend + Arabic RTL PWA
│   ├── app/                      # FastAPI server, auth, db, limit engine, adapters
│   ├── static/                   # Arabic RTL PWA shell (manifest + index)
│   ├── tests/                    # security + server-rule test modules
│   └── data/                     # per-tenant SQLite files + shared meta DB
└── README (this file)
```
Single-device pilot. **Only structure + design are mirrored here** — no source, no data.

## Design (what was built and verified via real calls)
- **Multi-tenant isolation**: each business gets its own SQLite DB; tenants + users live in a shared meta DB.
- **Auth + RBAC**: JWT auth; `owner`/`admin` vs `staff` roles. Staff cannot mutate wallets (403 enforced).
- **Configurable per-wallet caps (no schema migration to change)**: operating daily/monthly limits, provider MAX ceilings (warning only), and an informational tier. All changeable via API `PATCH`.
- **Active Limit Intelligence Engine** (the competitive wedge): per-wallet daily-used %, remaining, `at_risk` flag, **breach ETA** (minutes until cap at current throughput), and `reroute_to` suggestion. Rivals only show a passive 80% cap bar.
- **Cash in/out ledger** (manual entry — matches the shop's trust model) + tamper-evident activity log (who / when / what / wallet / amount).
- **Arabic RTL PWA shell** served at root: login, wallet cards with cap bars, cash entry, activity feed.
- **Bug capture (pilot QA)**: frontend `window.onerror` + `unhandledrejection` auto-capture, a manual in-app report button, and backend 500 middleware → stored and alerted to the owner via chat. Credentials are wired through env only, never in source.
- **SMS adapter skeleton** (later phase): a gateway adapter with idempotency / quarantine / signature verification, activated only when provider credentials exist.

## Stack
Python 3.11 · FastAPI · SQLAlchemy 2.x · SQLite-per-tenant · PBKDF2-HMAC password hashing (stdlib, no native deps) · JWT (python-jose) · vanilla JS PWA.

## Sanitized
- All secrets / `.env` values removed (signing secret, chat tokens, dev credentials). Only the architecture is described.
- No IP addresses or ports — described as a local dev server.
- No absolute home/server paths — replaced with a relative tree.
- No SSH keys or internal hostnames.
- No proprietary source — design-level overview only (client work).
- No client / shop name — described generically.

## Why it matters
Proof of building the **multi-tenant fintech-ledger layer**: tenant isolation, RBAC, configurable compliance caps, and an active limit-prediction engine. Demonstrates a local-first, offline-capable SaaS architecture for regulated cash-handling businesses.
