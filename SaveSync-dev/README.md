# SaveSync / SaveSync-dev (sanitized mirror)

> **Original:** private (`SaveSync-dev`) + public releases. Redacted overview — product + design only. No credentials or user data included.

## What it is
**SaveSync** — a local-first backup/sync/restore tool for PC game saves (Windows + Linux).
"Never lose your progress" — automatic, checksum-verified, account-free backups.

## Product (from public README)
- Automatic watching + backup of save folders (Steam-uncovered games, emulators, mod configs).
- **SHA-256 verified** copies — integrity checked, not just present.
- One-click restore; logs everything; restore pipeline tested as rigorously as backup.
- Cloud optional: Dropbox / Google Drive / OneDrive (user supplies own app credentials).
- No auto-upload, no telemetry; lightweight single executable.
- Status: v2.4.0-beta1 (beta; not code-signed yet).

## Engineering (from SaveSync-dev)
- Self-contained binary, no runtime dependencies.
- Windows 7/8/10/11 + Linux dev builds.
- Local-first: backups need no account, no internet.


