<p align="center">
  <img src="assets/hero.svg" alt="Mac Storage Cleanup hero" width="880">
</p>

# Mac Storage Cleanup — paid Codex skill

**Stop deleting. Start proving.**

<p align="center">
  <a href="docs/index.html">Landing page</a> ·
  <a href="mac-storage-cleanup.skill">Download skill</a> ·
  <a href="LICENSE-EULA.md">Paid terms</a> ·
  <a href="LICENSE-MIT.txt">MIT demo</a>
</p>

## What you are buying

A production-ready cleanup system that removes only generated project artifacts and duplicate files while keeping recovery and safety controls enabled by default.

- **No blind delete:** all actions are scoped, visible, and reversible.
- **No surprise loss:** active processes, credentials, personal media, and memories stay protected.
- **No trust games:** duplicate detection is SHA-256 exact and read-first.
- **No clutter in the final result:** manifest and post-action checks are included.

## What is inside the release

- `LICENSE-EULA.md`: commercial usage terms for paid redistribution.
- `LICENSE-MIT.txt`: public demonstration terms.
- `mac-storage-cleanup.skill`: installation package.
- `docs/index.html`: dedicated product page style shell.
- `SHA256SUMS`: integrity file for the release.

## Fast path to test

```bash
mkdir -p ~/.codex/skills
unzip -o mac-storage-cleanup.skill -d ~/.codex/skills
shasum -a 256 mac-storage-cleanup.skill
```

```bash
python3 mac-storage-cleanup/scripts/safe_generated_cleanup.py \
  --dry-run /absolute/project/.next /absolute/project/node_modules
```

```bash
python3 mac-storage-cleanup/scripts/safe_generated_cleanup.py \
  --apply --protect /absolute/critical/folder \
  /absolute/project/.next /absolute/project/node_modules
```

```bash
python3 mac-storage-cleanup/scripts/find_duplicate_files.py \
  --min-size 1048576 --protect /absolute/critical/folder /absolute/folder
```

## Safety contract

Only `.next` and `node_modules` are accepted for `/apply` cleanup.

If a target is ambiguous or active, the skill blocks the action.

`Warning/Default` is protected by default, and all manual overrides are explicit.

## Sales details

The paid product is distributed under `LICENSE-EULA.md`.

The demo package is intentionally limited to inspection and non-commercial use under `LICENSE-MIT.txt`.

## Contribution policy

This repo is curated for product quality.
Pull requests are accepted only with safety, verification, and license integrity in scope.
