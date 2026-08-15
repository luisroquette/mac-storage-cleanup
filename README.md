# Mac Storage Cleanup

### Free space without losing the plot.

Mac storage cleanup is usually a blunt instrument: delete until the number looks better, then discover what disappeared. **Mac Storage Cleanup** turns the job into an evidence trail.

![Mac Storage Cleanup hero](assets/hero.svg)

[Download the skill](mac-storage-cleanup.skill) · [Open the landing page](docs/index.html) · Fork after publishing

## The thesis

**Measure first. Touch less. Prove the result.**

This Codex skill handles the low-risk, high-volume work—generated project artifacts and exact duplicate files—while putting a hard stop in front of credentials, memories, personal media, protected folders, and active development processes.

## What it protects

- Active Vite, Next, Vitest, Electron, Python, Bun, and similar processes
- Source changes, manifests, lockfiles, and Git state
- Browser profiles, credentials, extensions, Claude/memory tooling, and project reports
- Personal media and existing Trash contents
- Any `Warning/Default` path, plus paths supplied with `--protect`

## What it can do

| Capability | Result |
| --- | --- |
| Generated-artifact cleanup | Dry-run `.next`/`node_modules` inventory, process guard, recoverable staging, manifest verification |
| Duplicate discovery | SHA-256 groups, read-only by default, canonical-file workflow |
| Safe deletion | Exact staging folder through Finder; never a blanket Trash empty |
| Operational reporting | Clear decisions, sizes, exit codes, and post-action disk space |

## Install

Download [`mac-storage-cleanup.skill`](mac-storage-cleanup.skill), then install it into your Codex skills directory:

```bash
mkdir -p ~/.codex/skills
unzip -o mac-storage-cleanup.skill -d ~/.codex/skills
```

Verify the release before installing:

```bash
shasum -a 256 mac-storage-cleanup.skill
cat SHA256SUMS
```

The skill is intentionally dry-run first. A destructive run requires an explicit `--apply` invocation after reviewing the exact targets.

## Use it

```bash
python3 mac-storage-cleanup/scripts/safe_generated_cleanup.py \
  --dry-run /absolute/project/.next /absolute/project/node_modules

python3 mac-storage-cleanup/scripts/safe_generated_cleanup.py \
  --apply --protect /absolute/critical/folder \
  /absolute/project/.next /absolute/project/node_modules
```

Find exact duplicate files without changing anything:

```bash
python3 mac-storage-cleanup/scripts/find_duplicate_files.py \
  --min-size 1048576 --protect /absolute/critical/folder /absolute/folder
```

## Why people keep it

Because the best cleanup is boring in the places that matter: no surprise logout, no vanished project memory, no “where did that folder go?” moment. The skill makes the safe path the obvious path—and leaves an audit-shaped trail when the work is done.

## Safety contract

This product does not promise that every file is disposable. It classifies uncertainty as a stop condition. Personal files, Downloads, Documents, Mail, Photos, iCloud data, and external-disk transfers require a separate review and explicit scope.

## Product status

The core skill is packaged and validated.

## Licensing model

This project uses a two-part release model:

- Paid product: proprietary EULA (`LICENSE-EULA.md`)
- Public demonstration version: MIT (`LICENSE-MIT.txt`)

The paid package is designed for commercial use with the guardrails in `LICENSE-EULA.md`.
The MIT license is only for demonstration materials you can share publicly for evaluation.

## Contributing

Fork it, run the dry-run tests, and open a focused pull request. Keep safety rules explicit, reproducible, and easy to audit.

---

### For a paid marketplace publish

Use the `LICENSE-EULA.md` terms for the distributable bundle.  
Keep `LICENSE-MIT.txt` only in the demo/trial package.
