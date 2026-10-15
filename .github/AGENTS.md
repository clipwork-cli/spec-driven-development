# Spec-driven Development AI Agent Guide

This repository uses an issue-driven, spec-driven workflow for modernization and Oracle to PostgreSQL migration.

AI agents assist engineering. Humans approve engineering decisions.

---

# Mission

- Understand before modifying.
- Preserve existing behavior.
- Follow engineering standards.
- Keep scope explicit and bounded.
- Produce reviewable artifacts and evidence.

---

# Canonical Workflow

Use this lifecycle and do not skip stages:

```text
Bootstrap
    ↓
Repository Context
    ↓
Runtime Context
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
```

---

# Issue-Driven Orchestration

GitHub Issues are the orchestration layer. Use these templates:

- `.github/ISSUE_TEMPLATE/bootstrap.yml`
- `.github/ISSUE_TEMPLATE/new-web-application.yml`
- `.github/ISSUE_TEMPLATE/specification.yml`
- `.github/ISSUE_TEMPLATE/planning.yml`
- `.github/ISSUE_TEMPLATE/implementation.yml`
- `.github/ISSUE_TEMPLATE/bugfix.yml`
- `.github/ISSUE_TEMPLATE/review.yml`

Expected flow:

1. Bootstrap issue opens discovery.
2. Discovery produces repository/runtime context artifacts.
3. Specification issues define one business capability per spec.
4. Planning issues produce executable work packages.
5. Implementation issues execute one work item at a time.
6. Bugfix issues resolve one verified defect within an approved specification boundary.
7. Review issues validate against specification, plan, standards, and evidence.

For a new mobile-friendly web application, start with
[`new-web-application.yml`](ISSUE_TEMPLATE/new-web-application.yml) to capture business
scope, technology preferences, visual theme, responsive/accessibility requirements,
identity and database-backed authorization, data, integrations, operations and acceptance
criteria. This is requirements intake, not a replacement for Bootstrap or approval to
implement. Complete discovery before creating one Specification issue per capability.
For an empty repository, record that runtime behavior is unavailable and request human
confirmation of the discovery approach; do not fabricate Runtime Context or bypass
agent preconditions.

---

# Repository Knowledge Sources

Always consume existing context before producing specs/plans/changes.

Repository Context:

```text
.ai/context/repository/
```

Runtime Context:

```text
.ai/context/runtime/
```

Specification Artifacts (canonical location):

```text
.ai/specifications/<spec-id>/
```

Canonical spec package files:

- `specification.md`
- `plan.md`
- `tasks.md`
- `review.md`
- `validation.md`

If required context is missing, recommend running the appropriate discovery stage first.

---

# Engineering Standards

Engineering standards are mandatory and take precedence over generic guidance.

Use:

```text
.ai/playbooks/
  oracle-to-postgresql/
  modernization/
```

---

# Agent Responsibilities

Each agent owns one stage:

- Static Discovery: Repository Context
- Runtime Discovery: Runtime Context
- Architect: Specification scope and boundaries
- Planner: implementation strategy and work items
- Developer: implementation of approved work items
- Reviewer: validation and findings

Do not combine multiple stages unless explicitly instructed.

---

# Guardrails

Always:

- Preserve behavior unless the approved specification explicitly allows change.
- Make incremental, reviewable changes.
- Update documentation when behavior/config/testing/deployment expectations change.
- Surface assumptions and risks.
- Keep traceability from capability → specification → plan → implementation → review → validation.

Never:

- Invent repository/runtime knowledge.
- Expand scope silently.
- Redesign architecture during implementation or review.
- Modify unrelated code.
- Bypass required human approval checkpoints.

---

# Unknowns and Approval

When information cannot be verified, explicitly write:

- `Unknown`
- `Requires Human Confirmation`

Human approval is required before:

- accepting repository/runtime context
- approving specifications and plans
- merging pull requests
- deploying to production
