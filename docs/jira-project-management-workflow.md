# Gatekeeper QA Jira Project Management Workflow

## 1. Purpose

This document defines how Gatekeeper QA uses Jira to plan, track, control, validate, and complete work throughout the delivery lifecycle.

The purpose of this workflow is to ensure that work does not move through the project arbitrarily. Each work item follows a controlled process with clear ownership, traceability, validation, and completion criteria.

The Jira workflow supports Gatekeeper QA's Quality Engineering approach by ensuring that implementation work is reviewed and validated before it is considered complete.

This standard applies to Gatekeeper QA internal engineering work, website development, QA initiatives, automation work, documentation, and other Jira-managed delivery activities.

---

## 2. Jira Work Item Structure

Gatekeeper QA uses Jira work items to organize and trace delivery work.

Typical work item types include:

- Epic — represents a large business or engineering objective.
- Story — represents user or business functionality.
- Task — represents implementation, configuration, documentation, or operational work.
- Bug — represents a confirmed defect requiring investigation or correction.
- Subtask — represents a smaller unit of work belonging to another work item.

Work items should be linked to the appropriate parent when applicable.

---

## 3. Work Item Requirements

Before work begins, a Jira work item should contain enough information for the assignee to understand what needs to be delivered.

Where applicable, this includes:

- Clear summary
- Description
- Business or technical context
- Requirements
- Acceptance criteria
- Priority
- Assignee or responsible owner
- Parent Epic or related work item
- Dependencies or blockers
- Relevant supporting information

The amount of detail should be proportional to the complexity and risk of the work.

---

## 4. Definition of Ready

A work item is ready to begin when the team has sufficient information to perform the work responsibly.

Before moving from To Do to In Progress, the team should understand:

- What needs to be delivered
- Why the work is required
- Relevant requirements
- Expected behavior or outcome
- Acceptance criteria where applicable
- Important dependencies
- Known risks or constraints

Missing information should be clarified before implementation when it could materially affect the result.

---

## 5. Workflow Statuses

Gatekeeper QA uses the following controlled Jira statuses.

### To Do

The work item has been identified but active work has not started.

### In Progress

The work is actively being implemented, investigated, configured, or documented.

### Ready for QA

Implementation work has been completed and the work item is waiting for QA validation.

Ready for QA does not mean Done.

### Blocked

Progress cannot continue because of a dependency, unresolved requirement, environment issue, technical problem, third-party dependency, or another blocking condition.

### Done

The work has completed the required workflow and passed the necessary validation.

Done is treated as a terminal state in the standard Gatekeeper QA workflow.

---

## 6. Controlled Transitions

Gatekeeper QA uses explicit workflow transitions rather than unrestricted status changes.

Primary delivery path:

To Do
↓ Start Work
In Progress
↓ Submit for QA
Ready for QA
↓ QA Passed
Done

Rework path:

Ready for QA
↓ QA Failed
In Progress

Blocked path:

In Progress
↓ Block Work
Blocked
↓ Resume Work
In Progress

These controlled transitions prevent work from bypassing required delivery and QA stages.

---

## 7. Start Work

The Start Work transition moves a work item from:

To Do → In Progress

The transition indicates that active work has begun.

Before starting work, the assignee should confirm that sufficient information exists to perform the task.

---

## 8. Submit for QA

The Submit for QA transition moves a work item from:

In Progress → Ready for QA

This transition indicates that implementation is complete from the assignee's perspective and the item is ready for independent validation.

Submitting work for QA does not mean that the work is complete.

---

## 9. QA Validation

QA validates the implementation against the applicable requirements, acceptance criteria, risks, and expected behavior.

Two outcomes are supported.

### QA Passed

Ready for QA → Done

QA Passed indicates that the required validation has been completed successfully.

### QA Failed

Ready for QA → In Progress

QA Failed indicates that the implementation does not yet satisfy the required acceptance criteria or has a blocking quality issue.

The work returns to In Progress for correction.

After correction, it must be submitted for QA again.

---

## 10. Blocked Work

If active work cannot continue, the Block Work transition is used:

In Progress → Blocked

The blocking reason should be recorded in Jira when appropriate.

Examples include:

- Missing requirement
- Environment unavailable
- External dependency
- Required access unavailable
- Technical dependency
- Third-party issue

Once the blocking condition is resolved:

Blocked → Resume Work → In Progress

Blocked work must not be marked Done simply because progress cannot continue.

---

## 11. Board Mapping

Gatekeeper QA uses a simplified board view while preserving detailed workflow states.

The board mapping is:

| Board Column | Workflow Status |
| --- | --- |
| To Do | To Do |
| In Progress | In Progress |
| In Progress | Ready for QA |
| In Progress | Blocked |
| Done | Done |

Ready for QA and Blocked remain unfinished work even though they represent different workflow states.

The workflow status provides the precise state of the work, while the board column provides a higher-level delivery view.

No required workflow status should remain unmapped.

---

## 12. Jira and Git Traceability

Engineering and documentation work managed through Git should maintain traceability to Jira.

The Jira key should be used where applicable in:

- Feature branch names
- Commit messages
- Pull request titles or descriptions
- Supporting documentation

Example branch:

feature/GKQA-5-jira-project-management-workflow

Example commit:

GKQA-5: define Jira project management workflow

This allows the team to trace Jira requirements to implementation and review history.

---

## 13. Evidence and Comments

Jira should contain enough information to understand the history and outcome of significant work.

Evidence may include:

- Pull request references
- Test results
- Screenshots
- Logs
- Defect references
- Review findings
- Relevant technical observations
- Decisions or clarifications

Comments should provide useful project history rather than unnecessary status noise.

---

## 14. Definition of Done

A work item may be considered genuinely complete when the applicable completion conditions have been satisfied.

Depending on the type of work, this may include:

- Required implementation completed
- Acceptance criteria satisfied
- Relevant testing completed
- Blocking defects resolved or appropriately handled
- Required evidence recorded
- Documentation updated
- Git changes reviewed
- Pull request approved and merged where applicable
- QA validation passed where required
- Jira information updated

A Jira status alone does not prove that the underlying work is complete.

---

## 15. Workflow Governance

Gatekeeper QA avoids unrestricted status transitions that allow work to bypass required controls.

Workflow changes should be deliberate and should support the actual delivery process.

The standard workflow should not be weakened simply to correct test data or move an incorrectly transitioned work item.

Any significant workflow change should be reviewed to determine its impact on:

- Delivery control
- QA validation
- Reporting
- Board visibility
- Traceability
- Existing work items

---

## 16. End-to-End Jira Delivery Workflow

The standard Gatekeeper QA Jira lifecycle is:

Work Identified
↓
Create Jira Work Item
↓
Define Scope / Requirements / Acceptance Criteria
↓
Prioritize
↓
Confirm Work Is Ready
↓
To Do
↓
Start Work
↓
In Progress
↓
Implementation / Documentation / Engineering Work
↓
Review and Local Validation
↓
Submit for QA
↓
Ready for QA
↓
QA Validation
↓
QA Passed
↓
Done

If QA fails:

Ready for QA
↓
QA Failed
↓
In Progress
↓
Correction
↓
Submit for QA

If work becomes blocked:

In Progress
↓
Block Work
↓
Blocked
↓
Resolve Blocking Condition
↓
Resume Work
↓
In Progress

---

## 17. Operating Principle

Jira is not simply a task list.

For Gatekeeper QA, Jira provides controlled visibility into what work exists, why it exists, who owns it, what state it is in, whether it has been validated, and whether it is genuinely complete.

The workflow supports Gatekeeper QA's broader principle:

Quality is built into the delivery process rather than inspected only at the end.