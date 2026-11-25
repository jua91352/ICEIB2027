## ADDED Requirements

### Requirement: Abstract follows the A–F story
The abstract in `latex/sections/00_abstract.tex` SHALL contain, in this order, one or two sentences for each A2Z checkpoint: A Attention Getter (evidence-based motivation), B But (challenge / research gap), C Cure (the proposed FMPA agent), D Development (method: store-price anchoring, RF/HGB, LLM + MCP tools), E Experiments (data, baselines, metrics), F Findings (results or expected outcomes).

#### Scenario: Reviewer traces the six checkpoints
- **WHEN** a reviewer reads the compiled abstract
- **THEN** each of A, B, C, D, E and F can be mapped to at least one sentence, in that order

#### Scenario: Source comments mark the checkpoints
- **WHEN** a co-author opens `00_abstract.tex`
- **THEN** LaTeX comments `% A` … `% F` label the sentence(s) for each checkpoint

### Requirement: Abstract is self-contained and honest
The abstract SHALL be a single paragraph of 150–250 words without citations, and SHALL NOT claim that the forecasting models outperform the no-change or momentum baselines.

#### Scenario: Negative result stated
- **WHEN** the abstract reports findings
- **THEN** it states that the learned models did not beat the simple baselines on the reported metrics

#### Scenario: Acronyms expanded
- **WHEN** an acronym such as LLM or MCP first appears in the abstract
- **THEN** its full form appears at that first use

### Requirement: IEEE keywords
The abstract file SHALL end with an `IEEEkeywords` environment listing 4–6 keywords that cover both AI and the domain.

#### Scenario: Keywords present
- **WHEN** the PDF is compiled
- **THEN** an "Index Terms" line appears with at least one AI keyword (e.g., LLM agent) and one domain keyword (e.g., vegetable price)
