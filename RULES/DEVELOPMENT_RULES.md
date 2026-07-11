# Development Rules

## Architecture

- Choose architecture according to the actual project requirements.
- Keep business logic separate from interface rendering.
- Keep data access separate from business logic.
- Avoid placing an entire application in one large file.
- Prefer clear modules with single responsibilities.
- Avoid unnecessary frameworks and dependencies.
- Design so that data sources can be replaced later when practical.

## Code quality

- Use descriptive names.
- Keep functions focused.
- Comment business rules and non-obvious decisions.
- Remove abandoned and duplicated code.
- Handle errors explicitly.
- Validate external and user-provided data.
- Do not silently ignore failures.

## Modification rules

Before changing an existing project:

1. Understand the current behavior.
2. Identify dependent functions.
3. Make the smallest safe change.
4. Test the modified behavior.
5. Retest related existing behavior.

## Dashboard rules

- KPI definitions must be documented.
- Filters must have explicit logic.
- Charts must not misrepresent scales or categories.
- Empty and partial data must be handled.
- Large datasets must not block the interface unnecessarily.

## Simulator rules

- Separate simulation engine, strategies and metrics.
- Document assumptions.
- Use the same input conditions when comparing strategies.
- Support reproducible runs when randomness is used.
- Include small deterministic test cases.
- Measure performance before optimizing.
- Use Web Workers or backend processing when browser work would block the interface.

## Operation tool rules

- Optimize the main input flow for speed and clarity.
- Prevent duplicate submission where practical.
- Validate required and optional fields.
- Display clear success and failure feedback.
- Separate frontend, data service and notification logic.
- Preserve record traceability.
