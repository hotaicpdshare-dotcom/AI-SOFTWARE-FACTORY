# Simulator Lifecycle

This document is a Simulator-specific overlay for `WORKFLOWS/GENERIC_PROJECT_LIFECYCLE.md`. Follow the generic stages, Gate rules, status template and skipped-Gate record; use the sections below for Simulator decisions only.

## Simulator Model Scope and Assumptions

### Objective

Define what the Simulator represents and what it deliberately does not represent.

### Required Inputs

- Simulation purpose and user decision
- Historical data or baseline conditions, when applicable
- Candidate inputs, constraints and known business rules

### Required Activities

- Decide whether the use case is historical replay, strategy comparison or another controlled experiment.
- Establish the current-state model and its boundaries.
- Record model assumptions, exclusions, units and expected uncertainty.

### Deliverables

- Simulation purpose and scope
- Current-state model outline
- Assumption and limitation register
- Required input and constraint list

### Exit Criteria

- The model scope is small enough to validate.
- Users understand what the output can and cannot claim.

### User Confirmation

**Gate S1 - Model scope and assumption confirmation:** The user confirms the model scope, assumptions, constraints and limitations.

## Simulator Strategy and Inputs

### Objective

Define comparable strategies, input conditions and measures.

### Required Inputs

- Gate S1 model scope
- Candidate strategy rules
- Baseline, initial conditions and comparison metrics

### Required Activities

- Define strategy rules without hiding business logic in presentation code.
- Define input conditions, parameters, units, ranges and constraints.
- Define comparison indicators and use the same input conditions for different strategies.
- Decide how randomness is controlled; use a fixed Seed when randomness exists.

### Deliverables

- Strategy definitions
- Input and parameter specification
- Comparison metric definitions
- Seed and reproducibility policy

### Exit Criteria

- Strategies are unambiguous and comparable.
- Inputs, units, ranges and metrics are testable.

### User Confirmation

**Gate S2 - Strategy definition confirmation:** The user confirms strategy rules, inputs, comparison metrics and random-seed policy.

## Simulator Verification Design

### Objective

Define evidence that distinguishes a correct model from an attractive animation or plausible-looking result.

### Required Inputs

- Confirmed model and strategy definitions
- Historical or baseline data
- Test and validation constraints

### Required Activities

- Build small deterministic test cases.
- Compare simulation results with historical data or known baselines.
- Separate model error from strategy effect.
- Define balance, conservation or invariant checks where applicable.
- Decide whether browser execution, Web Worker or Python/backend processing is appropriate.

### Deliverables

- Deterministic test cases
- Historical or baseline comparison plan
- Model-error versus strategy-effect review
- Execution architecture and performance test plan

### Exit Criteria

- The validation method can detect incorrect calculations.
- The model is not considered correct merely because the animation looks plausible.

### User Confirmation

**Gate S3 - Verification method confirmation:** The user confirms the deterministic tests, comparison method, validation boundaries and execution approach.

## Simulator Results and Limits

### Objective

Ensure users can interpret results without confusing them with observed facts or guaranteed predictions.

### Required Inputs

- Validated simulation outputs
- Historical comparison and uncertainty information
- User decision context

### Required Activities

- Label simulated, forecast, observed and recommended values separately.
- Explain result interpretation, uncertainty and model limitations near the output.
- For large simulations, provide progress, cancellation and a performance baseline.
- Check that visualization and animation do not conceal missing validation.

### Deliverables

- Result interpretation guide
- Limitation and uncertainty summary
- Performance and cancellation behavior
- User-facing distinction between model output and observed data

### Exit Criteria

- Users can state what a result means and what it does not prove.
- Results are reproducible from the same input, configuration and Seed.

### User Confirmation

**Gate S4 - Result interpretation and limitation confirmation:** The user confirms the result meaning, uncertainty, limitations and acceptable claims.

## Simulator Verification Checklist

During Generic Stage 6, verify:

- Deterministic test cases pass.
- Same input, configuration and Seed reproduce the same result.
- Different strategies use the same comparison conditions.
- Historical or baseline comparisons are visible.
- Model error is not misrepresented as strategy effect.
- Large simulations expose progress, cancellation and performance behavior where needed.
- Animation is not used as evidence of model correctness.

The current Simulator status should include Generic Gates plus S1, S2, S3 and S4, with the current model version and validation result.

