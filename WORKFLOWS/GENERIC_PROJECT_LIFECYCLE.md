# Generic Project Lifecycle

This workflow defines the shared lifecycle for Dashboard, Simulator, Operation Tool and Hybrid projects.

## How to Use

- Identify the current stage before taking action.
- Complete the required activities and record the deliverables.
- Do not pass an exit criterion based on an unconfirmed assumption.
- A small project may combine adjacent stages when the same decision and evidence cover both stages. Record the combined stages in Project Status.
- If a user explicitly asks to skip a Gate, record the decision, reason, date or context and risks before continuing.
- When a Gate is pending, stop and wait for user confirmation.

If the project involves Excel, CSV, Google Sheet, historical data, operational data or another dataset, use `PROMPTS/DATA_DISCOVERY.md` and `PROMPTS/ANALYSIS_REVIEW.md` as required in Stages 1 and 2. Use `RULES/DATA_RULES.md` for the detailed data requirements.

## Stage 0 - Intake

### Objective

Understand the request and establish the project's business context.

### Required Inputs

- User request or problem statement
- Intended users and stakeholders
- Available constraints, systems and timeline

### Required Activities

- Confirm the business purpose and expected outcome.
- Identify the primary user and the decision or action to support.
- Classify the project as Dashboard, Simulator, Operation Tool or Hybrid.

### Deliverables

- Requirement summary
- User and business purpose summary
- Project type and initial scope
- Initial assumptions and risks

### Exit Criteria

- The problem, user, expected outcome and project type are understood.
- Material questions that could change the solution are identified.

### User Confirmation

**Gate 0 - Intake confirmation:** The user confirms the purpose, users, expected outcome and project classification.

## Stage 1 - Data Discovery

### Objective

Understand whether available data can support the intended product or analysis.

### Required Inputs

- User-provided or connected datasets, when applicable
- Source ownership, access and refresh information
- Business definitions known by the user

### Required Activities

- For Excel, CSV, Google Sheet, historical or operational data, execute `PROMPTS/DATA_DISCOVERY.md`.
- Create a data dictionary and state what one record represents.
- Check missing values, duplicate values, field types, date range, unique values and abnormal values.
- Separate `raw`, `sample` and `processed` data; never overwrite raw data.
- Identify sensitive data, AI assumptions and unresolved questions.

### Deliverables

- Data source inventory
- Data dictionary
- Record-grain statement
- Data quality profile
- Assumption and uncertainty list

### Exit Criteria

- The data meaning, scope, limitations and quality issues are documented.
- Safe sample handling is defined where sensitive data exists.

### User Confirmation

**Gate A - Data understanding confirmation:** The user confirms that the AI's understanding of the data, fields, record grain and known limitations is correct.

## Stage 2 - Analysis Design

### Objective

Define a useful and defensible analysis direction before product design or implementation.

### Required Inputs

- Approved data understanding from Gate A
- Business questions and decisions to support
- Candidate metrics, comparisons and assumptions

### Required Activities

- Execute `PROMPTS/ANALYSIS_REVIEW.md` when the project uses data.
- Define the problem, KPI or comparison, baseline, scope and interpretation.
- Explain business meaning and identify misleading risks.
- Separate observed facts, calculated values, forecasts, simulations and recommendations.

### Deliverables

- Analysis question and intended decision
- KPI and metric definitions
- Comparison baseline and assumptions
- Misleading-risk review and mitigations
- Open decisions requiring the user

### Exit Criteria

- The proposed analysis answers a meaningful business question.
- KPI definitions, assumptions, limitations and risks are documented.

### User Confirmation

**Gate B - Analysis direction confirmation:** The user confirms the analysis direction, KPI, assumptions and business meaning.

## Stage 3 - Data Preparation

### Objective

Produce safe, validated and repeatable data for product use.

### Required Inputs

- Approved data understanding and analysis direction
- `raw` data or approved `sample` data
- Transformation rules and validation requirements

### Required Activities

- Preserve `raw`; use `sample` for development and create `processed` through documented transformations: `raw -> sample -> processed`.
- Build a repeatable cleaning, typing, joining and conversion process.
- Validate missing, duplicate, invalid, abnormal and incomplete data handling.
- Record source, transformation version, processing time and validation status.

### Deliverables

- Reproducible transformation process
- Processed dataset or data contract
- Validation report
- Data readiness decision and known limitations

### Exit Criteria

- The processed data meets the agreed product requirements.
- The same versioned input and configuration can reproduce the result.
- No unresolved issue materially invalidates the intended product use.

### User Confirmation

**Gate C - Data readiness confirmation:** The user confirms that the cleaned and transformed data is suitable for product use.

## Stage 4 - Product Design

### Objective

Turn the confirmed purpose, analysis and data into a practical product direction.

### Required Inputs

- Gate 0 through Gate C decisions, when applicable
- Project type and user workflow
- Processed data contract or approved no-data assumption

### Required Activities

- Define architecture, user flow, feature scope, interface areas and acceptance criteria.
- Decide what belongs in the minimum usable version.
- Identify security, performance, responsive and operational constraints.

### Deliverables

- Product requirements and scope
- Proposed architecture and data flow
- User flow or screen outline
- Acceptance criteria
- Implementation and test plan

### Exit Criteria

- The product direction is understandable and small enough to implement.
- Dependencies, risks and acceptance criteria are explicit.

### User Confirmation

**Gate D - Product direction confirmation:** The user confirms the architecture, scope, workflow and acceptance criteria.

## Stage 5 - Implementation

### Objective

Build a minimum usable product from confirmed requirements and approved data.

### Required Inputs

- Approved product design
- Safe sample or confirmed `processed` data
- Acceptance criteria and implementation plan

### Required Activities

- Build the minimum viable version first.
- Keep data access, business logic and presentation appropriately separated.
- Add validation, error handling and traceability.
- Keep the current stage and completion status updated.

### Deliverables

- Working implementation
- Updated data and business logic documentation
- Testable build or local preview
- Updated Project Status

### Exit Criteria

- The agreed core flow is implemented.
- The product can proceed to verification without known blocking implementation gaps.

### User Confirmation

No new mandatory Gate. Stop and request confirmation if implementation reveals a material scope, data or business-rule change.

## Stage 6 - Verification

### Objective

Verify functional correctness, data behavior and usable failure states.

### Required Inputs

- Working implementation
- Acceptance criteria
- Representative safe data and edge cases

### Required Activities

- Test the main flow, invalid input, empty data, loading and error states.
- Test data logic, responsive desktop and mobile behavior, and regression risks.
- For simulators, test deterministic cases and strategy calculations.

### Deliverables

- Verification results
- Defect and limitation list
- Regression result
- Preview readiness decision

### Exit Criteria

- No unresolved blocker prevents meaningful user review.
- Known limitations and failed checks are visible.

### User Confirmation

No new mandatory Gate. If verification changes the agreed meaning or acceptance criteria, return to the relevant prior Gate.

## Stage 7 - Preview and User Review

### Objective

Let intended users evaluate the product in a realistic preview environment.

### Required Inputs

- Verification-ready build
- Safe preview data or approved environment
- Review checklist and acceptance criteria

### Required Activities

- Deploy or provide a Preview.
- Observe whether users can complete the intended task and understand the result.
- Collect concrete modification requests and distinguish defects from scope changes.

### Deliverables

- Preview location or access method
- User review results
- Accepted changes and remaining issues

### Exit Criteria

- User review is complete and release blockers are identified.

### User Confirmation

**Gate E - Preview acceptance:** The user accepts the preview, requests changes, or explicitly accepts known limitations.

## Stage 8 - Release

### Objective

Release a controlled and supportable version.

### Required Inputs

- Accepted Preview
- Release checklist and deployment access
- Documentation, known limitations and rollback plan

### Required Activities

- Deploy the approved version.
- Update relevant documentation and version information.
- Record known limitations, monitoring needs and rollback steps.

### Deliverables

- Released product
- Release record
- Updated documentation
- Rollback method

### Exit Criteria

- The release is accessible and the rollback method is known.

### User Confirmation

**Gate F - Release authorization:** The user or designated owner authorizes release, or records why release is being deferred.

## Stage 9 - Continuous Improvement

### Objective

Improve the product and the factory through measured iteration.

### Required Inputs

- User feedback and usage evidence
- Defect, performance and support records
- Lessons learned

### Required Activities

- Review outcomes and prioritize the next iteration.
- Capture lessons learned and reusable components, templates or examples when valuable.
- Start the next change through the appropriate lifecycle stage.

### Deliverables

- Review summary
- Iteration backlog
- Lessons learned
- Reusable knowledge updates, when justified

### Exit Criteria

- The next action, owner and risk are clear.
- No documentation update is made solely for ceremony; small projects retain only useful evidence.

### User Confirmation

No new mandatory Gate. Confirm the next iteration when its scope or business direction is material.

## Project Status

Keep a short status record with the project. Update it when a stage starts, ends, a Gate is passed or a decision changes.

```text
Project:
Type:
Current Stage:
Stage Status: Not Started | In Progress | Waiting for Confirmation | Blocked | Complete
Completed Gates:
Pending Decisions:
Next Action:
Known Risks:
Last Updated:
```

## Skipped Gate Record

When a user explicitly requests skipping a Gate, append a short record:

```text
Skipped Gate:
User Decision:
Reason:
Risks Accepted:
Mitigation or Follow-up:
Date or Context:
```
