# ITERATION

This document defines how an existing software product should evolve.

The objective is to continuously improve the product while preserving stability.

Software should evolve through small, measurable improvements instead of repeated redesigns.

---

# Core Principle

Do not restart.

Do not rebuild.

Do not redesign everything.

Improve the existing product whenever practical.

Protect existing value.

Add new value.

---

# Step 0 — Understand the Current Product

Before making any changes, understand:

- Current functionality
- Existing architecture
- Previous design decisions
- Existing technical debt
- Previous user feedback
- Current deployment status

Never treat an existing product as a blank project.

---

# Step 1 — Classify the Requested Change

Identify what kind of change is being requested.

Choose one or more:

- New feature
- UI improvement
- UX improvement
- Performance improvement
- Bug fix
- Architecture improvement
- Data model change
- Business rule change
- Refactoring
- Deployment improvement

The classification determines the implementation strategy.

---

# Step 2 — Preserve Existing Value

Before implementing anything, identify:

What already works well?

What should never be broken?

What should remain unchanged?

Always preserve proven functionality whenever possible.

---

# Step 3 — Evaluate Impact

Estimate:

Files affected

Components affected

Business logic affected

User workflow affected

Deployment impact

Future maintenance impact

Prefer the smallest safe change.

---

# Step 4 — Improvement Strategy

For every requested change:

Describe

Current State

↓

Desired State

↓

Implementation Plan

↓

Expected Benefit

↓

Possible Side Effects

If several approaches exist,

briefly compare them and recommend one.

---

# Step 5 — Incremental Development

Implement in small iterations.

Each iteration should:

- Be independently testable
- Produce visible value
- Be easy to rollback
- Keep the product usable

Avoid combining unrelated changes.

---

# Step 6 — Regression Protection

After every iteration, verify:

Existing functions

New functions

Responsive layout

Performance

Business logic

Data integrity

Deployment

Never assume unchanged code still works.

Verify it.

---

# Step 7 — Knowledge Capture

Every completed iteration should improve the factory.

Update when appropriate:

LessonsLearned.md

Examples

Components

Templates

Design Rules

If new knowledge is created,

store it.

Do not let valuable experience disappear inside one project.

---

# Step 8 — Release Decision

Before release, determine:

Ready for production?

Preview required?

Need more testing?

Rollback plan available?

Known limitations?

Release only when the benefits outweigh the risks.

---

# Working Principles

Small improvements are better than large rewrites.

Continuous evolution is better than repeated redesign.

Maintainability is part of every iteration.

Prefer reusable components.

Reduce technical debt whenever practical.

Keep architecture clean.

---

# Communication Style

Explain:

What changed

Why it changed

Expected improvement

Possible impact

Future opportunities

Keep explanations concise.

Focus on engineering reasoning instead of implementation details.

---

# Success Criteria

A successful iteration should achieve all of the following:

- Solve the requested problem.
- Preserve existing value.
- Improve maintainability.
- Avoid unnecessary complexity.
- Leave the product in a better state than before.

# Evolution Mindset

Every project is part of a larger ecosystem.

Do not optimize only for the current request.

Whenever possible,

identify opportunities to:

- create reusable components
- improve templates
- improve prompts
- improve development workflow
- improve documentation

The goal is not only to improve this project.

The goal is to improve the entire AI Software Factory.

Every iteration should make future projects easier to build.
