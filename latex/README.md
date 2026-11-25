# FMPA paper — LaTeX source (ICEIB 2027, IEEE track)

Working copy of the paper. Built from the ICEIB 2027 IEEEtran starter (original kept in `../ICEIB paper/` and `../paper/before/`).

## Build on Overleaf

1. Zip this folder (or use `../paper/after/FMPA-ICEIB2027-after.zip`).
2. Overleaf → New Project → Upload Project.
3. Menu → Compiler: **pdfLaTeX**, Main document: **main.tex**.

Local build (needs TeX Live with IEEEtran, TikZ, tabularx, algorithmicx): `latexmk -pdf main.tex`.

## Layout

| Path | Content |
|---|---|
| `main.tex` | Preamble, title, macros (`\cnum`, `\todo`, `\tbd`), AI-use acknowledgment |
| `sections/00_abstract.tex` … `05_conclusion.tex` | One file per section; `% A`, `% G`, `% PA` … comments mark A2Z checkpoints |
| `figures/architecture.tex`, `figures/flowchart.tex` | TikZ figures (Fig. 1, Fig. 2) |
| `tables/article_summary.tex` | Table I — 8-column article summary (`table*`) |
| `tables/notation.tex`, `tables/comparison.tex` | Table II notation, Table III results |
| `references.bib` | Verified references only |

Red **TODO/TBD** markers in the PDF are values the authors must verify from the DIC3 experiment logs before submission.

## Editing with an agent + Overleaf MCP

The DIC4 workflow edits this folder with an AI agent (Claude Code or Antigravity) connected to Overleaf through an Overleaf MCP server. Keep the MCP configuration and any Overleaf token in your local, git-ignored settings (`.mcp.json`, `.claude/settings.local.json`) — never commit them. Work task by task from `../openspec/changes/draft-iceib2027-fmpa-paper/tasks.md`.
