# Design Rules

## General

- Use Traditional Chinese for the interface unless otherwise requested.
- Prioritize clarity over decoration.
- Use consistent spacing, typography and controls.
- Avoid crowded layouts.
- Important states must not rely on color alone.

## Responsive design

- Desktop is the primary workspace for dashboards and simulators.
- Operation tools must also work comfortably on mobile devices.
- Buttons and input controls must be easy to tap.
- Do not shrink text excessively to force content into one row.
- Reflow the layout instead of creating horizontal overflow where possible.

## Typography

- Default body text should normally be at least 16px.
- Labels, values and headings must have a clear hierarchy.
- Avoid oversized headings that reduce usable space.
- Numeric information must remain readable at a glance.

## Forms

- Clearly indicate required and optional fields.
- Keep the primary workflow short.
- Use appropriate input types.
- Preserve entered values when recoverable errors occur.
- Provide clear submission progress and result feedback.

## Dashboard

- Put the most decision-relevant information first.
- KPI cards must include clear definitions or context.
- Filters must be easy to find and understand.
- Charts must include meaningful labels and units.
- Detailed tables should support practical inspection.

## Simulator

- Separate configuration, execution and result areas.
- Show current strategy and input conditions.
- Display progress for long-running simulations.
- Make comparisons between strategies easy to understand.
- Explain assumptions and limitations near the results.

## Feedback-driven refinement

Treat user comments about size, spacing, order, readability and interaction as valid usability evidence.

Do not defend the current design merely because it is technically functional.
