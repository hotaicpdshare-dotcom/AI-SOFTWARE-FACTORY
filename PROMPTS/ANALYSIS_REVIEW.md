# ANALYSIS REVIEW

Use this prompt after data discovery and before implementing charts, simulation logic or operational summaries.

The objective is to confirm that the proposed analysis is useful, technically supported and not misleading.

## Step 1: State the Analysis Direction

Describe:

- The business question
- The decision or action the result should support
- The target users and their level of context
- The unit of analysis and time period
- The proposed measures, dimensions and comparisons
- What is explicitly out of scope

For every measure, reference its confirmed data definition and source fields.

## Step 2: Explain Business Meaning

For each KPI, chart, scenario output or operational summary, explain:

- What it means in business terms
- Why it matters to the user
- What action it may inform
- How it should be interpreted
- What it cannot prove or predict

Distinguish observed facts, calculated measures, forecasts, simulations and recommendations.

## Step 3: Review Misleading Risks

Check for:

- Correlation being presented as causation
- Incomplete periods being compared with complete periods
- Averages hiding distribution, volume or segment differences
- Small samples or unstable rates being overinterpreted
- Missing data or data collection changes altering the trend
- Duplicate records or joins inflating totals
- Choice of scale, denominator, category or time window distorting comparison
- Simulated or forecast values being presented as observed facts
- Precision, ranking or color implying confidence that the data does not support

For each risk, state the mitigation: label, filter, caveat, alternative metric, confidence range, disabled view or user confirmation.

## Step 4: Confirm Data and Transformation Support

Verify that:

- The record grain is understood and prevents double counting
- Required fields, dates, categories and relationships pass quality checks
- Raw data remains unchanged
- The result uses `sample` or approved data during development
- The transformation from `raw` or `sample` to `processed` is repeatable
- Missing, duplicate, invalid and abnormal values have documented handling
- The data dictionary and KPI definitions are complete

If any check fails, mark the analysis as not ready and identify the blocking decision.

## Step 5: Apply the Project-Type Review

### Dashboard

- Confirm that every KPI has a definition, denominator, aggregation and filter behavior.
- Reconcile headline totals to an approved source total.
- Confirm the treatment of empty, partial, delayed and incomplete periods.
- Review chart scales, units, ordering and labels for possible misinterpretation.

### Simulator

- Confirm the baseline, scenarios, assumptions, constraints and comparable input conditions.
- Explain the business meaning of outputs and the uncertainty around them.
- Verify deterministic cases and repeatability with the same input, configuration and seed.
- Ensure results are not described as predictions unless that claim has been validated and approved.

### Operation Tool

- Confirm that summaries reflect the operational record and current status definitions.
- Verify validation, duplicate prevention, idempotent retries, auditability and permission boundaries.
- Check that alerts or recommendations have an explicit rule, owner and safe failure behavior.
- Ensure users can distinguish submitted, processed, rejected and estimated values.

## Step 6: Produce the Review Decision

Return:

1. Analysis question and intended decision
2. Confirmed business definitions
3. Proposed outputs and interpretation guidance
4. Misleading risks and mitigations
5. Data quality and transformation readiness
6. AI assumptions and uncertainties
7. Open questions and decision owners
8. Decision: Approved, Approved with Conditions or Not Ready

Do not start visualization, simulation or operational implementation until the user confirms the analysis direction and any material assumptions. An approved direction must still preserve traceability to the data dictionary, quality profile and reproducible transformation.

