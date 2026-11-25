## ADDED Requirements

### Requirement: Numbered system architecture
Section III SHALL include an architecture figure whose main modules are numbered ① to ⑤ (user entry, MCP tools, host API, ForecastEngine, public historical data) and the text SHALL describe every numbered module.

#### Scenario: Figure and text agree
- **WHEN** a reviewer compares the architecture figure with the text of Section III
- **THEN** each module number in the figure is explained in the text and vice versa

### Requirement: Processing flowchart
Section III SHALL include a flowchart from Input → Check → AI/Analytics → Decision → Output, with a decision branch that returns an explicit error or clarification request when data are missing or confidence is low.

#### Scenario: Failure branch visible
- **WHEN** a reviewer reads the flowchart
- **THEN** a "no" branch from the data/confidence check leads to an error or clarification output instead of a forecast

### Requirement: Line-numbered pseudocode
Section III SHALL include Algorithm 1 written with `algorithmic` line numbers, in which the forecast value is produced only by the ForecastEngine tool call and never by the LLM.

#### Scenario: LLM boundary in the algorithm
- **WHEN** a reviewer reads Algorithm 1
- **THEN** the line that computes the forecast calls the forecasting tool, and the LLM appears only in intent parsing and explanation steps

### Requirement: Formal definition of modes A and B
Section III SHALL define the store-price-anchored forecast (mode A) and the momentum-adjusted forecast (mode B, fixed α = 0.3) with numbered equations and a notation table.

#### Scenario: Equations referenced
- **WHEN** Section IV describes mode A or mode B
- **THEN** it refers to the corresponding equation number with `\eqref`
