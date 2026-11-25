## ADDED Requirements

### Requirement: Verifiable references only
`latex/references.bib` SHALL contain only real sources that the authors can open (DOI or URL), and every `\cite` key in the paper SHALL exist in the bibliography.

#### Scenario: Undefined citation check
- **WHEN** the project is compiled on Overleaf
- **THEN** the log shows no "Citation ... undefined" warnings

### Requirement: Before and after versions are kept
The repository SHALL keep the untouched template as the "before" version (`paper/before/`) and a snapshot of the revised LaTeX as the "after" version (`paper/after/`), each with an Overleaf-uploadable zip.

#### Scenario: Teacher compares versions
- **WHEN** the teacher opens `paper/`
- **THEN** both versions are present and `paper/README.md` explains what changed per section

### Requirement: Builds on Overleaf within the page limit
The `latex/` project SHALL compile with pdfLaTeX on Overleaf using only packages available in TeX Live, and the compiled paper SHALL respect the conference page limit (4–8 pages).

#### Scenario: Overleaf compile
- **WHEN** `latex/` is uploaded to Overleaf as a new project with `main.tex` as the main document
- **THEN** it compiles without errors and produces a paper of at most 8 pages

### Requirement: AI-use disclosure
The paper SHALL include an acknowledgment or note that discloses which AI tools assisted literature search, drafting and LaTeX editing, and that the authors verified the content.

#### Scenario: Disclosure present
- **WHEN** a reviewer reads the end of the paper before the references
- **THEN** a short AI-assistance disclosure is present
