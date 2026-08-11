# helium-design-intelligence-saas (sanitized mirror — ARCHITECTURE ONLY)

> ⚠️ **Proprietary project.** No source is mirrored. This file describes the *architecture and
> engineering decisions* only, as evidence of full-stack SaaS capability. License: private.

## What it is (intent)
A design-prompt aggregation platform: a backend that ingests design references from
MIT-licensed public sources + user uploads, with tenant isolation, encryption, and hybrid search.

## Architecture (from source README)
- **Frontend:** Next.js 14 (React, SSR, Tailwind) — *scaffold only, no routes implemented*
- **Backend:** FastAPI (Python 3.12, async, Pydantic)
- **Database:** PostgreSQL 16 + pgvector (lexical + vector search)
- **Queue:** Redis 7 (Celery workers)
- **Storage:** MinIO (S3-compatible, AES-256-GCM encrypted)
- **Search:** Local hybrid search via Ollama `nomic-embed-text` (768-dim) + pgvector HNSW + RRF
- **Auth:** Clerk JWT, tenant isolation via PostgreSQL RLS

## Engineering scope (verified)
- **208 passing tests** across: encryption, storage, parsers, imports, catalog API, sitemap
  hardening, GitHub connector, auth, Celery, RLS, readiness, models.
- **DB roles:** owner / runtime-read / ingestion-write (least-privilege).
- **Content strategy:** public MIT catalog + metadata-only proprietary records + encrypted private imports.
- **Known limitations (honest):** frontend scaffold only; some phases not built; local Ollama dependency.

## Sanitized
- All `.env` keys, Clerk keys, MinIO creds, DB connection strings: **excluded**.
- API endpoint list: kept (it's design documentation, no secrets).
- No source files, no migrations, no seed data.

## Why it matters
Evidence of **shipping a tested, multi-service SaaS backend** (208 tests) with security primitives
(auth, RLS, encryption) — the level of engineering a funded AI startup operates at.
