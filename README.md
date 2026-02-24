# storygame-engine

**Make Your Own Story Game**
*A Non-Programmer’s Guide to Writing Interactive Fiction in YAML, Running a Proof-First Python Game, and Sharing Story Packs on GitHub*
By Nicholas Elliott Karlson

Website: **storygame.ca**


[![CI](https://img.shields.io/github/actions/workflow/status/nicholaskarlson/storygame-engine/verify.yml?branch=main&label=CI)](https://github.com/nicholaskarlson/storygame-engine/actions/workflows/verify.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## Frozen code anchor (for the book)

If you’re following the companion book, use the frozen tag:
- `book-v1.0`

```bash
git clone https://github.com/nicholaskarlson/storygame-engine
cd storygame-engine
git checkout book-v1.0
make verify
bash scripts/play.sh
```




A cross-platform Python text game (Ubuntu/macOS/Windows) where stories are authored in **plain YAML** and shared as deterministic **story packs** (zip + sha256 manifest + stable gallery index).

This repo is meant to support a companion book for non-programmers: you can write your own story game by editing `scenes.yaml` files—no Python required.

## What you can do

- **Play** a story in your terminal: `btg play`
- **Write** your own story by editing a single YAML file: `stories/<name>/scenes.yaml`
- **Validate** a story (catch authoring mistakes): `btg lint --strict --scenes ...`
- **Share** a story as a deterministic pack: `btg pack-story ... --out dist/packs/<name>.pack.zip`
- **Publish** a small gallery index for packs: `python scripts/build_packs.py`

## Quickstart (macOS / Ubuntu)

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install -U pip
python -m pip install -e ".[dev]"
btg play
```

## Quickstart (Windows PowerShell)

```powershell
python -m venv .venv
.\.venv\Scripts\python -m pip install -U pip
.\.venv\Scripts\python -m pip install -e '.[dev]'
.\.venv\Scripts\btg play
```


## One-command play scripts

- Windows PowerShell: `powershell -NoProfile -ExecutionPolicy Bypass -File scripts/play.ps1`
- macOS/Ubuntu: `bash scripts/play.sh`

(With no extra args, both default to `btg play --story starter`. To pass args, use `--` then the args.)

## If you're writing a story (non-programmer path)

Start here:

- **Authoring guide:** `docs/authoring.md`
- **Troubleshooting YAML:** `docs/troubleshooting.md`
- **Share packs + gallery:** `docs/sharing.md`
- **Command reference:** `docs/commands.md`

## Proof gate

On macOS/Ubuntu:

```bash
make verify
# or: bash scripts/verify.sh
```

On Windows (recommended):

```powershell
.\scripts\verify.ps1
```

`verify` runs formatting + lint + typecheck, story schema lint, tests, and builds deterministic share artifacts under `dist/` (packs + gallery index).

## Build share artifacts (packs + gallery)

macOS/Ubuntu:

```bash
make packs
# or:
python scripts/build_packs.py
```

Windows PowerShell:

```powershell
.\.venv\Scripts\python scripts\build_packs.py
```

Outputs are written under `dist/`.

## Repo layout

- `stories/` — story projects (each contains `scenes.yaml`)
- `game_content/scenes.yaml` — the repo’s default story content (used by examples/tests)
- `src/btg/` — the engine + CLI
- `dist/` — build outputs (packs + gallery index)

## License

MIT. See `LICENSE`.

## Project

- Contributing: `CONTRIBUTING.md`
- Support: `SUPPORT.md`
- Releases: `RELEASE.md`
