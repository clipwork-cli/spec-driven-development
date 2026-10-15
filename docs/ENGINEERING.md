# Spec-driven Development Engineering Framework

This document defines the engineering contract for repositories using Spec-driven Development.

AI assists delivery. Humans approve engineering decisions.

---

# Core principles

1. Understand before modifying.
2. Preserve existing behavior unless the approved specification says otherwise.
3. Keep scope explicit and bounded.
4. Use specifications for intent (`what`), plans for execution (`how`).
5. Deliver in small, reviewable increments.
6. Use evidence for validation and approval.

---

# Canonical lifecycle

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

Do not skip stages.

---

# Issue-driven orchestration

Use GitHub issue templates as the execution layer:

```text
.github/ISSUE_TEMPLATE/bootstrap.yml
.github/ISSUE_TEMPLATE/specification.yml
.github/ISSUE_TEMPLATE/planning.yml
.github/ISSUE_TEMPLATE/implementation.yml
.github/ISSUE_TEMPLATE/bugfix.yml
.github/ISSUE_TEMPLATE/review.yml
```

Expected flow:

1. Bootstrap issue opens discovery.
2. Static Discovery produces Repository Context.
3. Runtime Discovery produces Runtime Context and candidate specs.
4. Specification issue defines one capability slice.
5. Planning issue creates executable work items.
6. Implementation issues execute one work item each.
7. Review issues validate against specification, plan, standards, and evidence.

---

# Knowledge sources (mandatory)

Always use existing repository knowledge before generating new artifacts.

Repository Context:

```text
.ai/context/repository/
```

Runtime Context:

```text
.ai/context/runtime/
```

Engineering Standards:

```text
.ai/playbooks/oracle-to-postgresql/
.ai/playbooks/modernization/
```

---

# Specification package (canonical)

Every specification uses:

```text
.ai/specifications/<spec-id>/
```

Core artifacts:

- `specification.md`
- `plan.md`
- `tasks.md`
- `review.md`
- `validation.md`

Common supporting artifacts:

- `test-strategy.md`
- `rollback.md`
- `schema/` (when needed)

---

# Agent responsibilities

- **Static Discovery**: builds Repository Context only.
- **Runtime Discovery**: builds Runtime Context only.
- **Architect**: defines specification scope and boundaries.
- **Planner**: converts approved specification into executable plan artifacts.
- **Developer**: implements one approved work item per issue.
- **Reviewer**: validates implementation and evidence.

Do not combine stages unless explicitly directed.

---

# Guardrails

Always:

- preserve behavior outside approved scope
- maintain traceability: capability → specification → plan → implementation → review → validation
- document assumptions, risks, and constraints
- update docs when behavior, config, test, or deployment expectations change

Never:

- invent missing repository/runtime knowledge
- expand scope silently
- redesign architecture during implementation or review
- modify unrelated code

Unknown information must be written as:

- `Unknown`
- `Requires Human Confirmation`

---

# Human approval checkpoints

Human approval is required before:

- accepting Repository Context and Runtime Context
- approving specification and planning artifacts
- merging pull requests
- production deployment

---

# Working model for modernization and Oracle → PostgreSQL

Use capability-driven slicing:

- one specification per capability/slice
- one implementation issue per work item
- one reviewable PR per implementation issue

Candidate slice sequencing should come from:

```text
.ai/context/runtime/capabilities.md
```
