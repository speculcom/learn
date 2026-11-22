# Learn AI (learn.specul.com)

> 中文版：[README.md](./README.md)

The **concept layer** of the specul.com network: AI jargon arranged in six progressive stages, with a traceable primary source behind every term.

Live site: <https://learn.specul.com/>

## Scope

- 299 terms in six stages: Enter 36 · Use 44 · Use deeply 76 · Understand 60 · Run 46 · Choose 37.
- 111 mini-guides (5–10 minutes each) and 16 learning paths with checkpoints.
- Bilingual: every term has a Chinese entry, an English summary and a source list.
- Eight domains, four purposes and three observation axes are available as filters.

## Editorial rules

- **Write "unknown" when unknown.** No overall ranking of models or tools.
- Every claim carries a primary source and a verification date.
- A term's `level` must match its stage; the build gate rejects mismatched output.
- Facts are snapshots from the verification date, not permanent truth. Prices, versions and regional availability change; check the original source before relying on them.

## What this repository is

This is the **deployment repository** (`speculcom/learn`). It is built from `_data/handbook/terms` in the main workspace and published to GitHub Pages.

- Site files: `index.html`, `term/`, `guide/`, `path/`, `data/`, `2026.html`, `404.html`.
- Content source of truth: the `terms/` subtree of `speculcom/ai-handbook` — `terms/*.md`, `terms.en.json`, `paths/`, `guides/`, `meta.js`.
- **Do not edit generated files here.** They are overwritten on the next build. Edit `ai-handbook/terms`, then run the learn builder in the main workspace.

## Build and publish

```powershell
node _data\handbook\terms\scripts\build.mjs
node _toolchain\publish\publish.mjs --publish --inline-text --message "content: update learn"
```

The builder enforces a field-by-field equivalence gate: output must match the terms computed from `terms.en.json`; on a mismatch it exits without writing a partial build. Use `--accept` only after confirming an intentional field change; never bypass the gate by deleting the baseline.

## Licensing

Content is CC BY 4.0 (attribution required; commercial use allowed). Source code is MIT. The boundary between original and third-party material is stated at <https://specul.com/legal.html>.
