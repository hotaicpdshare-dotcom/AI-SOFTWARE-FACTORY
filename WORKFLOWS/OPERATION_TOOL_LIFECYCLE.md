# Operation Tool Lifecycle

This document is an Operation Tool-specific overlay for `WORKFLOWS/GENERIC_PROJECT_LIFECYCLE.md`. Follow the generic stages, Gate rules, status template and skipped-Gate record; use the sections below for frontline operation decisions only.

## Operation Context and Input Flow

### Objective

Design the shortest safe workflow for the real frontline context.

### Required Inputs

- Actual operating scenario and task frequency
- Primary device and network conditions
- User roles and permissions
- Existing paper, spreadsheet or system workflow

### Required Activities

- Identify the minimum actions needed to complete the task.
- Define required and optional fields.
- Choose scanning, typing, dropdown, button or other interaction methods.
- Prioritize mobile operation and keep important fields usable on small screens.

### Deliverables

- Field list and validation intent
- Role and device summary
- Shortest input flow
- Mobile usability constraints

### Exit Criteria

- The workflow reflects real operating conditions.
- Required information can be entered quickly without hiding important context.

### User Confirmation

**Gate O1 - Field and frontline workflow confirmation:** The user confirms the operating flow, devices, roles, required fields and interaction methods.

## Operation Data Write and Access

### Objective

Make record creation and retrieval safe, traceable and understandable.

### Required Inputs

- Gate O1 workflow and field definitions
- Google Sheet or other data source requirements
- Identity, permission and audit requirements

### Required Activities

- Define read, create, modify, query and status-tracking behavior.
- Define validation, duplicate prevention, idempotency and retry behavior.
- Define authentication, authorization and the minimum required data access.
- Record audit trail, source event, timestamps and processing version.

### Deliverables

- Data source and access decision
- Write and status transition rules
- Permission and identity model
- Audit and traceability plan

### Exit Criteria

- Valid writes, rejected writes, repeated submissions and retries are distinguishable.
- Users can trace records without exposing unnecessary sensitive data.

### User Confirmation

**Gate O2 - Data write and permission confirmation:** The user or data owner confirms write behavior, permissions, identity, auditability and traceability.

## Operation Notifications and Tracking

### Objective

Ensure notifications and follow-up status support operations without creating noise or ambiguity.

### Required Inputs

- Confirmed status transitions and ownership
- Notification channels and recipients
- Escalation and follow-up requirements

### Required Activities

- Define Email or other notification conditions, recipients, timing and failure behavior.
- Define submitted, processed, rejected, estimated and completed states.
- Define who owns each follow-up and how status is queried or updated.
- Preserve safe error messages and avoid logging confidential content unnecessarily.

### Deliverables

- Notification rules
- Status and follow-up model
- Ownership and escalation rules
- Notification failure handling

### Exit Criteria

- Every notification has an explicit trigger and owner.
- Users can distinguish record state from notification state.

### User Confirmation

**Gate O3 - Notification and tracking rule confirmation:** The user confirms notification conditions, recipients, statuses, ownership and follow-up behavior.

## Operation Reliability and Field UAT

### Objective

Prove that the tool remains safe and usable under real field conditions.

### Required Inputs

- Working operation flow
- Representative safe test records
- Mobile devices and network conditions
- Gate O1 through O3 decisions

### Required Activities

- Test success, failure, duplicate submission, timeout, offline or unstable network and resubmission paths.
- Verify clear write-success and write-failure feedback.
- Conduct field UAT on the primary mobile device and practical desktop fallback.
- Verify important fields, buttons and error messages remain usable at the actual screen size.
- Confirm audit trail and record traceability after retries.

### Deliverables

- Field UAT results
- Reliability and retry test results
- Mobile usability findings
- Release blockers and known limitations

### Exit Criteria

- Field users can complete the primary task and recover from expected failures.
- No unresolved issue risks duplicate, unauthorized or untraceable records.

### User Confirmation

**Gate O4 - Field UAT confirmation:** Field users or the designated owner confirm that the tool is usable and safe for the intended operation.

## Operation Tool Verification Checklist

During Generic Stage 6, verify:

- Required and optional fields are clear.
- Duplicate submission is prevented or safely handled.
- Successful and failed writes have clear feedback.
- Read, create, modify, query and status tracking follow the approved rules.
- Authentication and permissions are enforced, not merely hidden in the interface.
- Offline, unstable network, timeout and retry behavior is safe.
- Audit trail and data traceability are preserved.
- Mobile operation is comfortable and important fields are not cramped.

During Generic Stage 7, perform field UAT before release. The current Operation Tool status should include Generic Gates plus O1, O2, O3 and O4, with pending operational decisions and next action.

