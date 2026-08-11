# zserverai-infrastructure (sanitized mirror)

> **Original:** private. **Already sanitized by design** — the source repo ships only templates.
> This mirror preserves that: structure + safe migration docs, no real values.

## What it is
Infrastructure-as-code for a homelab rebuild: systemd units, Docker stacks, reverse-proxy
templates, and migration docs. Built to be **secret-free by default**.

## Verified structure
```
zserverai-infrastructure/
├── systemd/          # Custom systemd service units (templates)
├── docker/
│   ├── hdi/          # App stack: PostgreSQL, Redis, MinIO
│   └── gaming-pipeline/
├── caddy/            # Reverse-proxy route templates
├── ssh/              # SSH config TEMPLATES (placeholder IPs)
├── scripts/          # setup / restore scripts
├── manifests/        # System state snapshots (packages, containers, models)
└── docs/             # Migration planning
```

## Security posture (from source)
- ✅ No secrets — all `.env` are templates with placeholder values
- ✅ No database dumps — PostgreSQL/Redis/MinIO data git-ignored
- ✅ No SSH keys — config templates only, placeholder IPs
- ✅ No models — Ollama models excluded; only model *list* in manifests/
- ✅ No archives — backup tarballs/checksums excluded

## Sanitized further in this mirror
- Internal hostnames (`zserverai`, `zghost`): renamed to generic "homelab".
- Any remaining IP placeholders: kept as `10.0.0.0/24` style examples only.

## Why it matters
Shows I can **stand up and rebuild real infrastructure** (containers, services, proxy) reproducibly
— the backend discipline behind any deployed AI product.
