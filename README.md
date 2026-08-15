# Mac Storage Cleanup — paid Codex skill

<p align="center">
  <img src="assets/hero.svg" alt="Mac Storage Cleanup hero" width="900">
</p>

<p align="center">
  <strong>From panic deletion to controlled recovery.</strong><br>
  One command path from 90% guesswork to 100% traceability.
</p>

<p align="center">
  <a href="mac-storage-cleanup.skill">Download release</a> ·
  <a href="docs/index.html">Landing page</a> ·
  <a href="#license">Licensing</a> ·
  <a href="docs/index.html#proof">How it proves results</a>
</p>

## 1) What this is

**Mac Storage Cleanup** is a commercial Codex skill built for creators and teams that need macOS cleanup without irreversible mistakes.

It focuses only on the highest-risk storage waste for developers and power users:

- Project artifacts (`.next`, `node_modules`) that can be regenerated
- Exact duplicate files found by hash
- Recovery-safe staging before final cleanup

It is not a generic “delete-everything” utility.  
It is a **guard-first cleanup workflow**.

## 2) Why people pay for it

- You keep running apps, sessions, and project memory intact.
- You remove huge folders with an auditable, deterministic process.
- You get a clear **before/after signal** with size and safety checks.
- You avoid the classic failure: “I cleaned, then something important disappeared.”

## 3) Core architecture (what makes it non-generic)

### A) Dry-run hard gate
Every action starts as read-only analysis.  
You see exact targets, process state, manifest check, and estimated gain before anything can move.

### B) Multi-layer guardrails
- Active process protection (including dev tooling processes)
- Protected paths (`Warning/Default` and explicit `--protect`)
- Manifest/hash boundary validation (`package.json`, lockfiles, etc.)
- No blanket trash operations; everything goes to recoverable staging

### C) Post-action proof
- Manifest checks run again after the move
- Final delta and execution report is printed
- Any protected/inconsistent state aborts the run

### D) Scope discipline
Only two generated targets are eligible by default:
- `.next`
- `node_modules`

No broad folders, no wildcard cleanups.

## 4) Installation (2 minutes)

```bash
mkdir -p ~/.codex/skills
unzip -o mac-storage-cleanup.skill -d ~/.codex/skills
shasum -a 256 mac-storage-cleanup.skill
cat SHA256SUMS
```

## 5) Quick usage

Dry-run first:

```bash
python3 mac-storage-cleanup/scripts/safe_generated_cleanup.py \
  --dry-run /absolute/project/.next /absolute/project/node_modules
```

Apply with explicit safeguards:

```bash
python3 mac-storage-cleanup/scripts/safe_generated_cleanup.py \
  --apply --protect /absolute/critical/folder \
  /absolute/project/.next /absolute/project/node_modules
```

Discover exact duplicates (read-only):

```bash
python3 mac-storage-cleanup/scripts/find_duplicate_files.py \
  --min-size 1048576 --protect /absolute/critical/folder /absolute/folder
```

## 6) What you are buying

### Included in this release package
- Core skill bundle (`mac-storage-cleanup.skill`)
- Production-safe guard logic
- Verified duplicate discovery tool
- `LICENSE-EULA.md` for paid usage
- `LICENSE-MIT.txt` for demo usage
- Integrity checksum (`SHA256SUMS`)

### License model
- **Paid product:** proprietary EULA in [LICENSE-EULA.md](LICENSE-EULA.md)
- **Demo material:** MIT terms in [LICENSE-MIT.txt](LICENSE-MIT.txt)

## 7) Ideal customer / not for

**Ideal for**
- iOS/iOS-like macOS power users with repeated storage crises
- Freelance/agency developers with many project folders
- Teams managing many temporary build trees and dependencies

**Not for**
- People wanting automatic delete of photos, downloads, or entire drive folders
- Users who want silent background cleanup without explicit approval

## 8) Sales and delivery posture

This repo is positioned as a paid Codex skill product.  
The paid license is commercial; the MIT file is explicitly for demonstration workflows.

If you want this moved into a full checkout flow (Gumroad/Stripe/Paddle), I can integrate it in the next pass:
- custom pricing tiers
- support promises
- invoice automation
- update links in landing + README

## 9) Repository quality contract

- No unrelated changes in release branches
- No blanket trash clearing
- No silent data-risk actions
- No fallback heuristics for ambiguous cleanup targets
- Deterministic hashes and post-run reporting remain mandatory

## 10) Contributing

Only safety, validation, and product-hardening changes are accepted.
If you want a commercial patch, use focused PRs with explicit test and safety notes.

## License

- [EULA (commercial)](LICENSE-EULA.md)
- [MIT (demo)](LICENSE-MIT.txt)

