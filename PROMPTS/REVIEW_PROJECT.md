# REVIEW PROJECT

This document defines the standard workflow when modifying an existing software project.

The objective is to improve software safely without breaking existing functionality.

Never make changes immediately.

Understand first.

Analyze second.

Modify third.

Verify last.

---

# Step 0 — Understand Current System

Before making any modification:

Review:

- Current architecture
- Existing components
- Existing business logic
- Previous decisions
- Existing documentation
- Related examples

Never assume how the current system works.

Understand it first.

---

# Step 1 — Understand User Feedback

Summarize the user's feedback.

Examples:

"The text is too small."

"The simulator is slow."

"The KPI is confusing."

"The workflow feels complicated."

Translate subjective feedback into engineering requirements.

Example:

"The text is too small"

↓

Increase readability

↓

Review typography hierarchy

↓

Update design system if necessary.

---

# Step 2 — Root Cause Analysis

Identify the actual cause.

Separate symptoms from root causes.

Example:

Symptom

Loading is slow.

Possible causes

- Large dataset

- Too many DOM updates

- Blocking JavaScript

- Slow API

- Poor rendering

Do not modify code before identifying the likely root cause.

---

# Step 3 — Impact Analysis

Before changing anything, identify:

Which files will change?

Which modules may be affected?

Which existing features may break?

Estimate the impact.

Prefer the smallest safe modification.

---

# Step 4 — Improvement Proposal

Provide:

Problem

↓

Root Cause

↓

Possible Solutions

↓

Recommended Solution

↓

Expected Benefits

If multiple solutions exist,

compare them briefly.

---

# Step 5 — Implementation

Only after analysis,

modify the project.

Prefer:

Small commits

Small changes

Independent modules

Avoid unnecessary refactoring.

---

# Step 6 — Regression Testing

After modification,

verify:

Main function

Modified function

Related functions

Mobile

Desktop

Error handling

Loading

Edge cases

Never assume existing functions still work.

Verify them.

---

# Step 7 — Review Summary

Deliver:

Problem

Root Cause

Files Modified

Tests Performed

Expected Improvement

Remaining Risks

Future Suggestions

---

# Working Principles

Do not rewrite large amounts of code when a small modification solves the problem.

Respect existing architecture.

Improve maintainability whenever possible.

Keep the project stable.

---

# Continuous Improvement

Every modification should improve one or more of:

Readability

Usability

Performance

Reliability

Maintainability

Business value

Avoid changes that increase complexity without providing measurable value.

---

# Communication Style

Explain the reason before explaining the solution.

Focus on root cause instead of symptoms.

Use engineering thinking instead of personal opinion.

Recommend improvements when appropriate.

Challenge requests that may create long-term technical debt.

Think like a senior engineer reviewing production software.
