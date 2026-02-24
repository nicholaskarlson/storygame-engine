# Press-time checklist

Supports the book Make Your Own Story Game (Nicholas Elliott Karlson).
Website: storygame.ca
Note: the v1 CLI name is btg

Before the eBook is published:

- [ ] `main` is green in GitHub Actions
- [ ] README Quickstart works on Windows + macOS/Ubuntu
- [ ] `docs/authoring.md` is complete and matches current CLI flags
- [ ] `btg list-stories` shows starter projects
- [ ] `btg play --story starter` works from a clean checkout
- [ ] `python scripts/build_packs.py` produces `dist/packs/index.json`
- [ ] Create and push a tag for the book (e.g. `v0.1.0`)
- [ ] Make the repo public at press time (if currently private)
