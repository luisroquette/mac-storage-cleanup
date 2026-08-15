<div align="center">

# Mac Storage Cleanup

### Stop deleting. Start proving.

![Mac Storage Cleanup hero](assets/hero.svg)

[Download the skill](mac-storage-cleanup.skill) · [Open landing page](docs/index.html) · [Licença comercial (EULA)](LICENSE-EULA.md) · [MIT demo](LICENSE-MIT.txt)

</div>

## What this repo ships

This is a production-minded Codex skill for macOS cleanup with audit-grade behavior:

- Dry-run first for every operation
- Automatic process and manifest guards
- Recoverable staging before final deletion
- Duplicate discovery by exact SHA-256 fingerprint
- Strong default protections for credentials, media, memories and active projects

## Install

```bash
mkdir -p ~/.codex/skills
unzip -o mac-storage-cleanup.skill -d ~/.codex/skills
shasum -a 256 mac-storage-cleanup.skill
```

## Use it (safe-by-design)

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

## Why this model wins

- **Less risk**: active process and protected-path detection before action.
- **More certainty**: staging + manifest hash check keeps reversible decisions possible.
- **More control**: only `.next` and `node_modules` are candidates in `/apply`.

## Safety contract

This product is intentionally selective. Ambiguous targets are blocked and nothing is removed without explicit scope. Sensitive folders and `Warning/Default` remain protected by default.

## Licensing

- `LICENSE-EULA.md`: proprietary terms for the paid product
- `LICENSE-MIT.txt`: demo terms for public demonstration usage

## Contributing

Fork this repo only for review and adaptation experiments.  
No source code unrelated to cleanup safety is accepted.
