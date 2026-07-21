# sheetgen

LaTeX **worksheet template** in the [boulingua](https://github.com/boulingua)
design language, for generating printable exercise sheets that match the sister
sites and the [slidegen](https://github.com/boulingua/slidegen) slide decks.

> **Status — draft.** The style and an example worksheet are in place; a
> content-to-worksheet generator will follow.

## Design language

- **Fonts:** Source Sans 3 + JetBrains Mono — bundled in `fonts/`.
- **Accent:** boulingua blue `#1a73e8`; CEFR ramp (A `#4caf50`, B `#1a73e8`, C `#8e24aa`).
- **Watermark:** the boulingua logo + author **S. Le Boulanger** in the **lower-left of every page**.
- Clean sections with accent rules, a level badge, answer-key boxes and writing lines.

## Usage

```bash
make example          # or: xelatex worksheet-template.tex  (run twice)
```

Requires **XeLaTeX** or **LuaLaTeX** (for `fontspec`). In your own sheet:

```latex
\documentclass[11pt]{article}
\usepackage{boulingua-sheet}
\worksheetheader{Title}{Subtitle}{Niveau M}{blgcefrB}
```

Helpers: `\worksheetheader`, `\blgbadge`, `\blglines[n]`, and the `blganswers` box.

## Files

- `boulingua-sheet.sty` — the style package
- `worksheet-template.tex` — worked example
- `fonts/`, `assets/boulingua-logo.png` — bundled assets

## Licence

Code MIT (see `LICENSE`). The boulingua logo and name are used under the project's own terms.

## Use of LLM tools

Portions of this project were prepared with assistance from large language model tooling for narrowly defined, non-authorial tasks: copyediting, prose smoothing, Markdown/LaTeX formatting, scaffolding of boilerplate files (CI configs, build scripts), code refactoring. The tools used were Chat AI, the LLM service of KISSKI (GWDG), and a self-hosted Mistral Small (24B, Apache-2.0) run locally via Ollama and the ollamar R package — local inference only, with no data sent to third parties for the self-hosted model.
