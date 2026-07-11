# AI Workflow

This document defines how the AI developer must work on every project.

## 1. Understand before building

Before writing code, identify:

- The problem being solved
- The intended users
- The expected outcome
- The available data
- The operating environment
- The main constraints

Do not begin implementation when a missing decision could materially change the architecture.

For minor ambiguity, state a reasonable assumption and continue.

## 2. Classify the project

Every project must first be classified as one of the following:

### Dashboard

Primary purpose:

- Present information clearly
- Support monitoring and decision-making
- Provide filters, KPI indicators, charts and detailed records

### Simulator

Primary purpose:

- Reproduce a process or system
- Test alternative strategies
- Compare results under controlled assumptions
- Produce auditable and repeatable results

### Operation Tool

Primary purpose:

- Support fast frontline input
- Validate and save records
- Summarize information
- Send notifications
- Support follow-up and status tracking

A hybrid project may use more than one category, but the primary category must be identified.

## 3. Plan before coding

Before implementation, produce:

1. Requirement summary
2. Assumptions
3. Risks
4. Proposed architecture
5. Data flow
6. Task breakdown
7. Acceptance criteria

Keep the plan proportionate to the project size.

## 4. Build incrementally

Use this order:

1. Minimum working version
2. Core business logic
3. Error handling
4. Responsive interface
5. Automated tests
6. Performance improvements
7. Deployment

Do not add unnecessary features merely because they are technically possible.

## 5. Test before delivery

At minimum, verify:

- Main user flow
- Invalid input
- Empty data
- Loading state
- Error state
- Desktop layout
- Mobile layout
- Existing functions after modification
- Deployment build

For a simulator, also verify deterministic test cases and strategy calculations.

## 6. Deliver clearly

Every delivery must state:

- What was completed
- Which files changed
- What was tested
- How to access the preview
- Known limitations
- Decisions requiring user confirmation

Do not report a feature as completed unless it has been implemented and checked.

## 7. Protect stable versions

Do not directly break or replace a known working version.

Prefer:

- Feature branch for development
- Preview before release
- Main branch for stable releases
- Small, traceable commits

## 8. Respond to feedback precisely

When the user says things such as:

- Text is too large
- A control is too small
- The process feels slow
- The logic does not match reality

Treat the feedback as a product requirement.

Identify the affected component, make the smallest safe modification, retest related functions, and report the change.
