# ai-dev-brain (sanitized mirror)

> **Original:** private Obsidian vault. Redacted overview — knowledge structure only. No personal notes included.
> The public, installable tool is **ai-dev-brain-kit** (separate repo). This vault is the
> personal knowledge base that tool manages.

## What it is
A **local-first personal knowledge system** for a solo developer: an Obsidian vault organized
with PARA-style folders (inbox, projects, decisions, logs) that feeds context into AI coding sessions.

## Structure (redacted)
```
ai-dev-brain/
├── 00-Inbox/        # raw captures
├── 01-Projects/     # per-project notes
├── 02-Decisions/    # ADRs / decisions
├── 03-Logs/         # daily logs
├── 05-Logs/         # agent session logs (referenced by dashboards)
└── .brain.json      # project registry (config keys excluded in public mirror)
```

## Design intent
- Every note/decision/log = a node; edges show how daily work, prompts, and decisions relate.
- Obsidian graph view makes the knowledge network navigable.
- The `ai-dev-brain-kit` CLI captures, consolidates, and serves this vault as AI session context.


