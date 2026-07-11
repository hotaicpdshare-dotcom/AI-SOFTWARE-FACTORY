# Data Rules

This document defines the minimum data preparation, validation and approval requirements for every Dashboard, Simulator and Operation Tool project.

## 1. Data Understanding Before Development

Before visualization, simulation or operational workflow implementation, document:

- The business purpose and intended users
- The source, owner and update frequency of each dataset
- What one record represents (the grain of the data)
- The time zone, date semantics and reporting period
- The meaning, unit and valid range of each important field
- The business definitions of metrics, statuses and categories
- The AI assumptions and unresolved uncertainties

Do not begin visualization or simulation until the user confirms the business definitions and analysis direction.

## 2. Required Data Layers

Use three distinct data layers:

- `raw`: Original source data retained for traceability. Raw data must never be directly overwritten, cleaned in place or silently replaced.
- `sample`: Safe development data, such as synthetic, anonymized or approved extracts. Company-sensitive data must not be used as a default development fixture.
- `processed`: Reproducibly transformed data used by the application, with documented transformations and validation results.

Keep the layers separate. Record the source, transformation version, processing time and validation status for every processed dataset.

## 3. Sensitive Data and Repository Safety

Company-sensitive data, personal data, credentials and confidential datasets must not be pushed to GitHub by default. Use anonymized or synthetic samples and add appropriate ignore rules before local data is introduced. Never commit secrets or confidential content merely to make a feature easier to demonstrate.

## 4. Data Dictionary

Every project must create and maintain a data dictionary. At minimum, each relevant field must include:

- Field name and display name
- Data type and storage format
- Business definition
- Unit and allowed values or range
- Whether the field is required, nullable or derived
- Example value using safe sample data
- Source field and transformation rule, when applicable
- Sensitivity classification and access considerations

Metric definitions must also state the numerator, denominator, filters, aggregation method and reporting period.

## 5. Minimum Data Quality Profile

Before use, profile each input and processed dataset and record:

- Row count and column count
- Missing values by field, including percentage and handling decision
- Duplicate values and duplicate records, including the definition of a duplicate
- Date range, date format, time zone and future or impossible dates
- Unique values and unexpected category values for categorical fields
- Field types, inferred types and type conversion failures
- Outliers and other abnormal values, including the detection rule and disposition
- Referential integrity, key uniqueness and relationship gaps when related tables exist
- Whether the data is complete and current enough for the intended decision

Do not silently drop, fill or recode records. Document the rule, impact and resulting record counts for each decision.

## 6. Repeatable Transformations

Data transformations must be executable repeatedly and produce the same result for the same versioned input and configuration. Prefer version-controlled scripts or clearly documented queries over manual spreadsheet edits. A transformation must define its inputs, outputs, ordering, timezone handling, null handling, deduplication rule, validation checks and failure behavior.

## 7. Assumptions and Confirmation Gate

List every AI assumption, inferred business rule and unresolved uncertainty separately from confirmed facts. Mark the owner and decision needed for each item.

Without explicit user confirmation of the data meaning, business definitions, analysis direction and material assumptions, do not start visualization, simulation or production-like operational behavior. A prototype may inspect safe samples, but it must not present unconfirmed results as business truth.

## 8. Project-Specific Requirements

### Dashboard

- Prepare a reporting-ready processed dataset with stable dimensions, metric definitions and a known refresh period.
- Validate filter fields, aggregation levels, date coverage, units, category labels and KPI reconciliation against source totals.
- Check that missing or partial periods are visible and that charts do not imply unsupported precision, continuity or causation.
- Document the dashboard grain, filter logic, KPI formulas and the meaning of empty states.

### Simulator

- Prepare explicit inputs, parameters, constraints, baseline conditions and scenario data separately from observed history.
- Validate units, ranges, initial conditions, time steps, random seeds and the comparability of scenarios.
- Verify deterministic test cases, conservation or balance rules where applicable, and reproducibility from the same input and seed.
- Label assumptions, forecast outputs and uncertainty clearly; do not treat simulated outcomes as observed facts.

### Operation Tool

- Prepare input validation rules, required fields, reference data, status transitions and duplicate-prevention keys.
- Validate field formats, permissions, allowed transitions, idempotency, timestamps, audit fields and error recovery behavior.
- Verify that saved records remain traceable to the user, source event and processing version without exposing unnecessary sensitive data.
- Test incomplete, repeated, invalid and offline or retry submissions where relevant.

## 9. Data Readiness Record

Before implementation approval, retain:

1. Data source and ownership summary
2. Record-grain statement
3. Data dictionary
4. Data quality profile and issue decisions
5. Transformation plan and reproducibility instructions
6. AI assumptions and uncertainties
7. Analysis review and user confirmation

