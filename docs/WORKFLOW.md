# Spec-driven Development Workflow

This document defines the operational workflow for issue-driven, spec-driven engineering.

---

# End-to-end lifecycle

```text
Bootstrap
    ↓
Static Discovery
    ↓
Runtime Discovery
    ↓
Specification
    ↓
Planning
    ↓
Implementation
    ↓
Review
    ↓
Validation
    ↓
Human Approval
    ↓
Merge
```

---

# Stage owners and outputs

| Stage | Owner | Primary Output |
| --- | --- | --- |
| Bootstrap | Engineer | Bootstrap issue |
| Static Discovery | Static Discovery | `.ai/context/repository/*` |
| Runtime Discovery | Runtime Discovery | `.ai/context/runtime/*` |
| Specification | Architect | `.ai/specifications/SPEC-XXX/specification.md` |
| Planning | Planner | `plan.md`, `tasks.md`, `test-strategy.md`, `rollback.md` |
| Implementation | Developer | One PR for one work item |
| Review | Reviewer | `review.md` + recommendation |
| Validation | Developer + Reviewer | `validation.md` evidence |
| Human Approval | Engineer / Tech Lead | Merge decision |

---

# Issue templates

Use these templates:

```text
.github/ISSUE_TEMPLATE/bootstrap.yml
.github/ISSUE_TEMPLATE/specification.yml
.github/ISSUE_TEMPLATE/planning.yml
.github/ISSUE_TEMPLATE/implementation.yml
.github/ISSUE_TEMPLATE/bugfix.yml
.github/ISSUE_TEMPLATE/review.yml
```

---

# Execution flow

## 1. Bootstrap issue

Create bootstrap issue and define objective, assumptions, applicable standards, and discovery activities.

## 2. Static Discovery

Assign bootstrap issue to Static Discovery and generate Repository Context.

## 3. Runtime Discovery

Assign bootstrap issue to Runtime Discovery and generate Runtime Context.

Runtime Discovery should populate candidate engineering specifications in:

```text
.ai/context/runtime/capabilities.md
```

## 4. Close bootstrap issue

Close only after discovery artifacts are reviewed and accepted.

## 5. Specification issues

Create one specification issue per capability slice.

Assign to Architect and produce one `specification.md` per slice.

## 6. Planning issues

For each approved specification, create one planning issue.

Assign to Planner and produce plan artifacts in `.ai/specifications/SPEC-XXX/`.

## 7. Implementation issues

Split `tasks.md` into one issue per execution work item.

Assign each issue to Developer.

Rule: one work item per issue, one PR per issue.

## 8. Review issues

Create review issue per implementation PR and assign Reviewer.

Reviewer validates specification compliance, standards, behavior preservation, and evidence.

## 9. Continue by slice

Move to the next capability specification and repeat.

---

# Decision gates

| Gate | Decision |
| --- | --- |
| Bootstrap | Ready for discovery |
| Discovery | Repository and runtime context approved |
| Specification | Scope approved |
| Planning | Ready for implementation |
| Implementation | Ready for review/validation |
| Review | Approve / changes required |
| Human approval | Merge approved |

No gate should be skipped.

---

# Rules of engagement

Always:

- preserve behavior unless approved spec explicitly changes it
- keep scope bounded to the active capability or work item
- follow `.ai/playbooks/oracle-to-postgresql/*` and `.ai/playbooks/modernization/*`
- keep traceability across all artifacts

Never:

- implement before discovery/spec/planning approvals
- expand scope silently
- redesign architecture during implementation or review

Unknowns must be explicitly documented as `Unknown` or `Requires Human Confirmation`.
