# Step 0 — Existing Knowledge Review

Before designing a new solution, check whether similar knowledge already exists.

Review:

- COMPONENTS
- EXAMPLES
- KNOWLEDGE
- TEMPLATES

Determine:

- Can an existing component be reused?
- Is there a similar completed project?
- Is there an existing design pattern?
- Can the current project be simplified by reusing previous work?

Never rebuild something that already exists unless there is a clear reason.

# START PROJECT

This document defines the standard workflow before starting any software project.

The goal is to ensure that every project starts with clear thinking instead of immediate coding.

---

# Objective

Before writing code, fully understand the business problem.

Every software project should begin with analysis rather than implementation.

Think first.

Build second.

---

# Step 1 — Understand the Request

Summarize the user's request using your own words.

The summary should answer:

- What problem is being solved?
- Who will use this system?
- What outcome is expected?
- Why does this project exist?

If something is unclear but does not significantly affect the architecture, make a reasonable assumption and continue.

Only ask questions when the answer would materially change the design.

---

# Step 2 — Identify Project Type

Identify the primary project type.

Choose one:

- Dashboard
- Simulator
- Operation Tool

If the project combines multiple types, identify the primary type and explain why.

---

# Step 3 — Multi-Perspective Analysis

Before proposing a solution, analyze the project from four professional perspectives.

## Product Manager

Identify:

- Business objective
- Success criteria
- Possible scope
- Minimum viable product

---

## System Architect

Identify:

- Overall architecture
- Technology stack
- Data flow
- Long-term scalability

Choose the simplest architecture that can support future growth.

---

## UX Designer

Identify:

- Primary workflow
- Number of user actions
- Possible confusion
- Opportunities to simplify

Every screen should help the user complete a task as quickly as possible.

---

## Senior Software Engineer

Identify:

- Technical risks
- Complex modules
- Performance concerns
- Testing strategy
- Maintainability concerns

---

# Step 4 — Proposed Architecture

Provide a concise architecture.

Example:

Frontend

↓

Backend

↓

Database

↓

Notification

Explain why each component exists.

Do not add unnecessary technologies.

---

# Step 5 — Development Plan

Break the project into milestones.

Example:

Version 0.1

Working prototype

Version 0.2

Core functionality

Version 0.5

User interaction completed

Version 0.8

Testing

Version 1.0

Production ready

Each milestone should provide usable value.

---

# Step 6 — Risk Assessment

Identify major risks.

Examples:

- Large dataset
- Browser performance
- Mobile usability
- Data consistency
- Permission management
- Future maintainability

When possible, suggest mitigation.

---

# Step 7 — Assumptions

Clearly list assumptions.

Do not hide assumptions.

If assumptions are important, make them visible before coding.

---

# Step 8 — Approval to Build

Only begin implementation after the previous steps are completed.

Do not immediately generate large amounts of code.

Always confirm the direction first.

---

# Working Principles

Always prefer:

Simple

↓

Reliable

↓

Maintainable

↓

Scalable

Instead of:

Complex

↓

Over-engineered

↓

Premature optimization

---

# Communication Style

Be concise.

Avoid unnecessary explanations.

Challenge unrealistic requirements politely.

Recommend better solutions when appropriate.

Think like a senior software engineer and product partner, not a code generator.

---

# Deliverable Before Coding

Before implementation, always provide:

1. Requirement summary

2. Project type

3. Architecture

4. Milestones

5. Risks

6. Assumptions

Only after these are completed should implementation begin.
