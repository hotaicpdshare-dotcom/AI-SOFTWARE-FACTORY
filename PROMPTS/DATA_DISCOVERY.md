# DATA DISCOVERY

Use this prompt before developing any Dashboard, Simulator or Operation Tool.

The objective is to understand the data before visualizing, simulating or designing an operational workflow.

## Step 1: Identify the Business Context

Summarize:

- The problem and intended decision or action
- The users and data owner
- The project type: Dashboard, Simulator or Operation Tool
- The expected outcome and reporting or operating frequency

If the project is hybrid, identify the primary type and explain the different data needs.

## Step 2: Inventory the Data

For every source, record:

- Source name, owner and access method
- Source format, refresh frequency and date coverage
- Whether it contains company-sensitive or personal data
- Related tables, keys and known limitations
- Which copy belongs to `raw`, `sample` or `processed`

Never overwrite the original source. Use safe synthetic, anonymized or approved sample data for development, and do not assume sensitive data may be pushed to GitHub.

## Step 3: Define the Record Grain

Write one clear sentence answering:

> What does one row represent?

Also identify the unique key, time grain, entity grain, joins and any risk of double counting. If the answer is uncertain, stop and list the alternatives for user confirmation.

## Step 4: Build the Data Dictionary

Create a dictionary covering every field used by business logic or the interface. Include field name, type, definition, unit, allowed values, nullability, example safe value, source, transformation and sensitivity classification.

Define every KPI or derived measure with its formula, aggregation, filters, denominator and reporting period.

## Step 5: Profile Data Quality

Report, by dataset and field:

- Missing values and percentages
- Duplicate values and duplicate records
- Date range, format, time zone and invalid dates
- Unique values and unexpected categories
- Field types and conversion failures
- Outliers and abnormal values
- Key, relationship and completeness issues

For every issue, state the detection rule, affected records, proposed handling and business impact. Do not silently discard or repair data.

## Step 6: Plan the Transformation

Describe the repeatable process from `raw` or approved `sample` to `processed` data. Specify cleaning, typing, joins, deduplication, null handling, derived fields, timezone conversion, validation checks, versioning and failure behavior.

Manual edits are not an acceptable substitute for a reproducible transformation when the result will be used by the application.

## Step 7: Record Assumptions and Uncertainty

Separate confirmed facts from AI assumptions, inferred meanings and unresolved questions. For each uncertain item, record its possible impact and the person who must confirm it.

## Step 8: Apply the Project-Type Checklist

### Dashboard

- Confirm reporting grain, KPI formulas, filter logic, date completeness and reconciliation totals.
- Define how missing, partial and empty periods will appear.
- Check that visual encodings do not imply unsupported precision or causation.

### Simulator

- Separate observed data, model inputs, parameters, constraints and scenarios.
- Confirm units, ranges, initial conditions, time steps, random seed policy and baseline.
- Define deterministic test cases and reproducibility checks.

### Operation Tool

- Define required inputs, reference data, status transitions, duplicate keys and audit fields.
- Validate formats, permissions, idempotency, retries and traceability.
- Test incomplete, invalid and repeated submissions.

## Step 9: Deliver for Approval

Return the following before implementation:

1. Business and source summary
2. Record-grain statement
3. Data dictionary
4. Quality profile and issue decisions
5. Transformation plan
6. Assumptions and uncertainty list
7. Project-type validation checklist
8. Questions requiring user confirmation

Do not begin visualization, simulation or operational behavior until the user confirms the data meaning, business definitions and analysis direction.

