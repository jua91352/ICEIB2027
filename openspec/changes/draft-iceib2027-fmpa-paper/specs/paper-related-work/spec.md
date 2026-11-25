## ADDED Requirements

### Requirement: Balanced AI and domain coverage
Section II SHALL contain one subsection on AI technology (price forecasting models, simple-baseline evidence, LLM agents and tool use including MCP) and one subsection on domain know-how (retail price stickiness, wholesale-to-retail price transmission, weather/typhoon shocks, public price data), with a roughly equal number of cited works in each.

#### Scenario: Count of citations per side
- **WHEN** a reviewer counts distinct citations in the AI subsection and the domain subsection
- **THEN** neither side has fewer than one third of the total

### Requirement: Article Summary Table
Section II SHALL include a table with the eight columns Ref., Year, Problem, AI Method, Domain Knowledge, Dataset, Findings and Limitation, covering at least six cited works, with at least two from 2024 or later.

#### Scenario: Table compiles in two-column layout
- **WHEN** the PDF is compiled with the IEEEtran conference class
- **THEN** the table appears as a full-width `table*` float without overflowing the page margins

#### Scenario: Every row is a real reference
- **WHEN** a reviewer follows the citation in any table row
- **THEN** it resolves to an entry in `references.bib` that has a DOI or a working URL

### Requirement: Research gap synthesis
Section II SHALL end with a paragraph that follows Existing Research → Limitations → Research Gap → Our Project, naming the three gaps FMPA addresses: no store-price anchor, no fixed 7/14 calendar-day evaluation against naive baselines, and no agent that keeps numeric forecasting outside the LLM.

#### Scenario: Gap paragraph present
- **WHEN** a reviewer reads the last subsection of Section II
- **THEN** the three gaps are listed and each is linked to a component of the proposed scheme
