# Sharing stories (packs + gallery)

Supports the book Make Your Own Story Game (Nicholas Elliott Karlson).
Website: storygame.ca
Note: the v1 CLI name is btg

A **story pack** is a deterministic zip file that contains:

- `scenes.yaml` (your story)
- optional extra files inside your story folder (README, assets)

Each pack also contains a deterministic manifest and checksum list so others can verify integrity.

## Build a single pack

```bash
btg pack-story stories/my_story --out dist/packs/my_story.pack.zip
```

Verify a pack:

```bash
btg verify-pack dist/packs/my_story.pack.zip
```

## Build the gallery index

Build packs for everything in `stories/` and write:

- `dist/packs/index.json`

```bash
python scripts/build_packs.py
```

This is designed for “proof-first” sharing: deterministic outputs and stable hashing.
