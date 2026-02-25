# Deep Learning at Scale for the GPU Poor

Lecture notes for COMP70010 at Imperial College London, by Dr Harry Coppock.

## Quick start

```sh
uv sync
uv run quarto preview --port 4000
```

## Building

```sh
uv run quarto render
```

Output is written to `_site/`.

## Deployment

Pushing to `main` triggers the GitHub Actions workflow (`.github/workflows/publish.yml`) which builds the Quarto site and deploys it to GitHub Pages.

## File structure

```
_quarto.yml                       # Quarto book config
custom.scss                       # Tufte-style theme + callout colors
mathjax-macros.html               # Custom math macros (\R, \FLOPs, etc.)
pyproject.toml                    # Python/uv project (quarto-cli dependency)
index.qmd                        # Preface (landing page)
chapters/
  computational-foundations.qmd   # Chapter 1: Number representation, memory, FLOPs, scaling laws
  moe-and-peft.qmd               # Chapter 2: Mixture of Experts, LoRA, QLoRA
  precision-caching-inference.qmd # Chapter 3: Mixed precision, KV caching, MLA
  practice-questions.qmd          # Practice exam questions
appendices/
  symbols.qmd                    # List of symbols
figures/                          # PNGs + pre-rendered TikZ SVGs
tikz-standalone/                  # TikZ source + compiled PDFs for diagram SVGs
references.bib                   # Bibliography
.github/workflows/
  publish.yml                    # Quarto -> GitHub Pages
```

## Theorem environments

| Environment | Quarto syntax | Colour |
|---|---|---|
| Definition | `::: {#def-name}` | Green |
| Theorem | `::: {#thm-name}` | Red |
| Lemma | `::: {#lem-name}` | Red |
| Corollary | `::: {#cor-name}` | Red |
| Proposition | `::: {#prp-name}` | Red |
| Example | `::: {#exm-name}` | Blue |
| Remark / Note | `.callout-note appearance="simple"` | Blue line |
| Exam question | `.callout-caution` | Grey |

## Credits

Template structure inspired by [Gilles Castel](https://castel.dev)'s lecture notes setup and the Tufte-LaTeX project.
