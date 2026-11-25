## ADDED Requirements

### Requirement: Reproducible experimental setup
Section IV SHALL state the data source (13 public markets in Taichung City), sample sizes (7-day n = 2,085; 14-day n = 1,859), the chronological train/test split, the label-maturity rule used to prevent leakage, the models (RandomForest for 7 days, HistGradientBoosting for 14 days) and the software used.

#### Scenario: Leakage rule stated
- **WHEN** a reviewer looks for how future information is excluded
- **THEN** the text explains that samples whose t+h label had not matured at the split date were removed before training

### Requirement: Fair baselines and metrics
Section IV SHALL compare the models with a no-change (persistence) baseline and a momentum baseline using direction macro-F1 (higher is better) and relative-change MAE (lower is better), and SHALL define both metrics with equations.

#### Scenario: Metric direction is explicit
- **WHEN** a reader looks at the results table
- **THEN** the column headers show ↑ for macro-F1 and ↓ for MAE

### Requirement: No fabricated results
Section IV SHALL contain only numbers that the author has verified against the DIC3 experiment logs; until then, result cells SHALL be marked with a visible TODO placeholder, and the qualitative finding that the models did not beat the baselines SHALL be reported.

#### Scenario: Unverified numbers
- **WHEN** the measured values have not yet been copied from the DIC3 logs
- **THEN** the results table shows a highlighted TODO marker rather than invented values
