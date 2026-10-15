# Getting Started

Spec-driven Development is an issue-driven, spec-driven workflow for AI-assisted engineering.

This guide shows the fastest way to onboard a real repository.

---

# What to copy into the target repository

Copy all three folders:

```text
.ai/
.github/
docs/
```

`docs/` is required because agents reference `docs/ENGINEERING.md`.

After copying, update `.github/CODEOWNERS`, `.github/CODE_OF_CONDUCT.md`,
`.github/CONTRIBUTING.md`, and `.github/GOVERNANCE.md` for your repository.

---

# Required references

Before creating issues, review:

```text
docs/ENGINEERING.md
docs/WORKFLOW.md
.github/AGENTS.md
.github/copilot-instructions.md
```

---

# Step-by-step onboarding flow

## 1. Bootstrap

Create a bootstrap issue using:

```text
.github/ISSUE_TEMPLATE/bootstrap.yml
```

Fill in repository objective, standards, assumptions, and discovery scope.

## 2. Static Discovery

Assign the bootstrap issue to **Static Discovery**.

Expected outputs:

```text
.ai/context/repository/*
```

## 3. Runtime Discovery

Assign the same bootstrap issue to **Runtime Discovery**.

Expected outputs:

```text
.ai/context/runtime/*
```

`capabilities.md` should include candidate engineering specifications.

## 4. Close Bootstrap

After human review of discovery outputs, close the bootstrap issue.

## 5. Specification (one capability slice per issue)

Create a specification issue using:

```text
.github/ISSUE_TEMPLATE/specification.yml
```

Assign to **Architect**.

Rules:

- one specification for one modernization capability slice
- preserve existing behavior
- no planning details
- no implementation details

Expected output:

```text
.ai/specifications/SPEC-XXX/specification.md
```

Use capability priorities from:

```text
.ai/context/runtime/capabilities.md
```

## 6. Planning

Create a planning issue using:

```text
.github/ISSUE_TEMPLATE/planning.yml
```

Assign to **Planner**.

Expected outputs in `.ai/specifications/SPEC-XXX/`:

- `plan.md`
- `tasks.md`
- `test-strategy.md`
- `rollback.md`

## 7. Implementation (one issue per work item)

Split `tasks.md` into implementation issues using:

```text
.github/ISSUE_TEMPLATE/implementation.yml
```

Assign each issue to **Developer**.

Rules:

- implement exactly one approved work item per issue
- produce one reviewable PR per issue
- update tests/docs required by the work item
- refresh `.ai/specifications/SPEC-XXX/validation.md`

## 8. Review

Create review issues using:

```text
.github/ISSUE_TEMPLATE/review.yml
```

Assign to **Reviewer**.

Reviewer validates scope, standards, behavior preservation, and evidence.

## 9. Repeat per specification

When one specification slice is complete, move to the next candidate slice.

---

# Optional prompt starters

Use the optional prompts from the repository `README.md` section:

- Architect prompt starter
- Planner prompt starter
- Developer prompt starter

---

# Success criteria

Onboarding is complete when:

- Repository Context and Runtime Context are approved
- capability slices are represented as specifications
- each specification has plan and tasks
- implementation is delivered one work item per issue/PR
- review and validation evidence are present per work item
