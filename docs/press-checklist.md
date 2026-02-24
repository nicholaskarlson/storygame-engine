# Press-time checklist

Before you publish the KDP eBook:

- [ ] `main` is green in GitHub Actions
- [ ] README Quickstart works on Windows + macOS/Ubuntu
- [ ] `docs/authoring.md` is complete and matches current CLI flags
- [ ] `btg list-stories` shows starter projects
- [ ] `btg play --story starter` works from a clean checkout
- [ ] `python scripts/build_packs.py` produces `dist/packs/index.json`
- [ ] Create and push a tag for the book (e.g. `v0.1.0`)
- [ ] Make the repo public at press time (if currently private)
