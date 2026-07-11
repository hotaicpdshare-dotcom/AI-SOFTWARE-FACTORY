# Dashboard Lifecycle

This document is a Dashboard-specific overlay for `WORKFLOWS/GENERIC_PROJECT_LIFECYCLE.md`. Follow the generic stages, Gate rules, status template and skipped-Gate record; use the sections below for Dashboard decisions only.

## Dashboard Starting Decision

### Objective

Confirm whether the Dashboard is a one-way information display or an interactive decision-support tool.

### Required Inputs

- Intended users and business purpose
- Decisions users must make
- Approved data understanding and analysis direction, when data is involved

### Required Activities

- State the decision the Dashboard should support.
- Choose static display, filters, drill-down, comparison or other interaction only when it serves that decision.
- Identify the primary device and expected usage frequency.

### Deliverables

- Dashboard purpose statement
- User decision statement
- Display-versus-interaction decision

### Exit Criteria

- The Dashboard has a clear job and audience.
- Every proposed interaction has a decision-related reason.

### User Confirmation

No Dashboard-specific Gate. Use Generic Gate 0 and Gate D for the baseline direction.

## Dashboard Metrics and Narrative

### Objective

Define metrics that can be understood, calculated and traced to data.

### Required Inputs

- Gate A data understanding
- Gate B analysis direction
- Data dictionary and source fields

### Required Activities

- Define KPI formula, numerator, denominator, aggregation, filters, unit and reporting period.
- Define the analysis narrative and the intended interpretation.
- Check that every KPI is traceable to fields and a reproducible calculation.

### Deliverables

- KPI Definition list
- Analysis narrative
- Traceability map from KPI to fields and formulas
- Misleading-risk mitigations

### Exit Criteria

- No KPI depends on an undocumented business definition.
- The narrative does not imply unsupported causation, precision or completeness.

### User Confirmation

**Gate D1 - KPI and analysis narrative confirmation:** The user confirms the KPI definitions, narrative, assumptions and interpretation limits.

## Dashboard Information Design

### Objective

Specify a layout and interaction model that helps users find and understand important information quickly.

### Required Inputs

- Confirmed KPI and narrative
- User tasks and device constraints
- Available dimensions and categories

### Required Activities

- Define filters and Filter Logic, including default values and empty behavior.
- Create Chart and Table Specification with titles, units, scales, ordering and source metrics.
- Put decision-relevant information first and avoid visual choices that distort comparison.

### Deliverables

- Layout outline
- Filter Logic specification
- Chart and Table Specification
- Empty and partial-data behavior

### Exit Criteria

- Users can identify the main decision information without guessing.
- Filters, charts and tables have explicit behavior and definitions.

### User Confirmation

**Gate D2 - Layout and interaction direction confirmation:** The user confirms the layout, filters, charts, tables and interaction behavior.

## Dashboard Data Delivery and Performance

### Objective

Choose a reliable data delivery method and make refresh and scale behavior explicit.

### Required Inputs

- Gate C processed data readiness
- Dataset size and refresh needs
- Security, access and hosting constraints

### Required Activities

- Choose static data, Google Sheet or API based on freshness, access, security and scale.
- Define Data Refresh Strategy, ownership, frequency, failure behavior and timestamp display.
- Define handling for empty, partial, delayed and stale data.
- Assess large-data performance and whether filtering, aggregation, pagination or backend processing is needed.

### Deliverables

- Data Refresh Strategy
- Data source and access decision
- Empty and partial-data states
- Performance risks and mitigation plan

### Exit Criteria

- Data delivery, refresh and access decisions are explicit.
- The Dashboard does not silently present stale or partial data as complete.

### User Confirmation

**Gate D3 - Data update method confirmation:** The user confirms the chosen static data, Google Sheet or API approach, refresh behavior and limitations.

## Dashboard Preview Acceptance

During Generic Stage 7, verify:

- Users can understand the Dashboard quickly.
- Users can find anomalies without excessive searching.
- Filters are intuitive and produce expected results.
- KPI values reconcile to approved source totals.
- Empty, partial and delayed data states are understandable.
- The experience works on desktop and mobile.
- Charts and tables do not mislead through scale, color, ordering or missing context.

The current Dashboard status should include Generic Gates plus D1, D2 and D3, with any pending decision and next action.

