## ADDED Requirements

### Requirement: Introduction follows G–L checkpoints
Section I SHALL be organized by the A2Z checkpoints G General (current situation, with cited public evidence), H However (challenges), I In literature (categories of existing solutions, old to new), J Judgement (strengths and weaknesses of those categories), K Keypoint (design spirit, novelty, contributions) and L List the organization.

#### Scenario: Evidence-based opening
- **WHEN** a reviewer reads the first paragraph of Section I
- **THEN** it cites at least one verifiable public source (government statistic, report or paper) rather than a generic claim such as "AI is developing rapidly"

#### Scenario: Organization paragraph
- **WHEN** a reviewer reaches the end of Section I
- **THEN** a paragraph names every later section using `\ref` labels

### Requirement: Research questions and contributions are explicit
Section I SHALL state RQ1 (7-day and 14-day forecasting effectiveness), RQ2 (gain from the A/B input modes), RQ3 (feasibility of low-effort natural-language querying) and an itemized list of contributions C1–C3 that map to those questions.

#### Scenario: RQ to contribution mapping
- **WHEN** a reviewer compares the RQ list with the contribution list
- **THEN** every contribution refers to at least one RQ and no contribution claims a result that Section IV does not support
