# Spec-driven Development

> An Engineering Framework for AI-Assisted Software Delivery

---

## Overview

Spec-driven Development is a framework that standardizes how software engineering work is discovered, planned, implemented, and reviewed using AI assistants.

Unlike prompt libraries or AI coding tools, Spec-driven Development does not prescribe how code should be written. Instead, it defines a repeatable engineering workflow where humans remain responsible for architectural decisions while AI assists with analysis, planning, implementation, and review.

The framework is designed to be independent of any specific AI tool. While the reference implementation uses GitHub Copilot, the engineering workflow is applicable to any AI-assisted development environment.

---

## Design Principles

Spec-driven Development is founded on the following principles.

- Understand before modifying.
- Preserve existing behaviour.
- Specifications define intent.
- Plans define execution.
- AI assists; humans approve.
- Engineering knowledge should be reusable.
- Business capabilities take precedence over technical layers.
- Prefer incremental delivery over large rewrites.
- Evidence is more valuable than assumptions.

---

## Why Spec-driven Development?

Large legacy systems are difficult to modernize because engineering knowledge is often undocumented, inconsistent, or distributed across teams.

Traditional AI coding workflows typically begin with implementation.

Spec-driven Development takes a different approach.

It separates engineering into distinct stages:

1. Discover the application.
2. Build repository knowledge.
3. Define business capabilities.
4. Produce specifications.
5. Generate implementation plans.
6. Implement.
7. Review.
8. Validate.

This produces repeatable, reviewable engineering outcomes while reducing implementation risk.

---

# Engineering Workflow

Every feature follows the same lifecycle.

```text
Repository
    │
    ▼
Bootstrap
    │
    ▼
Repository Context
    │
    ▼
Runtime Context
    │
    ▼
Feature Discovery
    │
    ▼
Specification
    │
    ▼
Implementation Plan
    │
    ▼
Implementation
    │
    ▼
Review
    │
    ▼
Evidence
```

Each stage produces artifacts that become the inputs to the next stage.

---

# Template Onboarding Workflow (Recommended)

Use this sequence when you copy `.ai/`, `.github/`, and `docs/` into a real application repository.

After copying, update community-health files in `.github/` to match your target repository ownership and policies:
`CODEOWNERS`, `CODE_OF_CONDUCT.md`, `CONTRIBUTING.md`, and `GOVERNANCE.md`.

1. Create a **Bootstrap** issue using `.github/ISSUE_TEMPLATE/bootstrap.yml`.
2. Fill in repository objective, standards, and discovery scope.
3. Assign discovery in order:
   - **Static Discovery** agent to build `.ai/context/repository/*`
   - **Runtime Discovery** agent to build `.ai/context/runtime/*`
4. Review discovery outputs, then close the bootstrap issue.
5. Open one **Specification** issue per capability slice (from `.ai/context/runtime/capabilities.md`, especially **Candidate Engineering Specifications**).
6. Assign the **Architect** agent and produce `.ai/specifications/SPEC-XXX/specification.md` for one capability only.
7. After spec approval, open a **Planning** issue and assign the **Planner** agent to produce:
   - `plan.md`
   - `tasks.md`
   - `test-strategy.md`
   - `rollback.md`
8. Split `tasks.md` into **one implementation issue per execution work item**.
9. Assign each implementation issue to the **Developer** agent; produce one PR per issue.
10. Run **Review** issues with the **Reviewer** agent and finalize validation evidence.
11. Move to the next specification slice and repeat.

This keeps scope bounded, preserves behavior, and makes modernization work reviewable and parallelizable.

---

# Prompt Starters (Optional Issue Prompts)

These prompts are intended for the optional prompt field when assigning issues to agents.

**Architect**

```text
Create one specification for one modernization capability/slice only.

Issue: #<issue-number>
Capability: <from issue>
Objective: <from issue>
Use:
- .ai/context/repository/*
- .ai/context/runtime/*
- .ai/playbooks/oracle-to-postgresql/*
- .ai/specifications/README.md

Tasks:
1. Produce .ai/specifications/SPEC-XXX/specification.md
2. Keep scope to one capability.
3. Include explicit in-scope, out-of-scope, risks, assumptions, constraints, and acceptance criteria.
4. Preserve existing behavior.
5. No planning, no implementation details.

Output:
- specification.md ready for human approval.
```

**Planner**

```text
Transform approved specification into executable plan artifacts.

Issue: #<issue-number>
Specification: .ai/specifications/SPEC-XXX/specification.md

Tasks:
1. Produce in .ai/specifications/SPEC-XXX/:
   - plan.md
   - tasks.md
   - test-strategy.md
   - rollback.md
2. Define phased execution work items (small, reviewable, behavior-safe).
3. Include dependencies, risks, validation strategy, and rollback triggers.
4. No production code changes.
```

**Developer**

```text
Implement exactly one approved execution work item.

Issue: #<issue-number>
Specification: .ai/specifications/SPEC-XXX/specification.md
Plan: .ai/specifications/SPEC-XXX/plan.md
Tasks: .ai/specifications/SPEC-XXX/tasks.md
Work item: <from issue>

Tasks:
1. Implement only this work item.
2. Preserve behavior and stay in scope.
3. Update tests/docs as required by the task.
4. Produce/refresh validation evidence in:
   - .ai/specifications/SPEC-XXX/validation.md
5. Prepare PR.

Output:
- One reviewable PR for one work item.
```

---

# Core Concepts

Spec-driven Development distinguishes between four different kinds of engineering knowledge.

## Repository Context

Long-lived knowledge describing the repository.

Examples

- Architecture
- Dependencies
- Repository Structure
- Testing Strategy
- Modernization Opportunities

Repository Context changes infrequently.

---

## Runtime Context

Knowledge describing application behaviour.

Examples

- Business Capabilities
- Runtime Operations
- Code Flows
- Entry Points
- External Integrations

Runtime Context explains how the application behaves.

---

## Engineering Standards

Engineering Standards capture reusable engineering practices.

Examples

- Oracle → PostgreSQL Migration
- Legacy Modernization
- Framework Upgrade
- API Design
- Testcontainers

Standards are written by architects.

Standards are consumed by AI.

---

## Feature Context

Feature Context describes one engineering initiative.

Examples

- Oracle Migration – Inventory
- Oracle Migration – Reporting
- Authentication Modernization

Each feature owns its own Specification, Plan, Tasks and Review.

---

# AI Workflow

AI participates in engineering through specialised agents.

Each agent has one responsibility.

| Agent             | Responsibility                             |
| ----------------- | ------------------------------------------ |
| Static Discovery  | Build Repository Context                   |
| Runtime Discovery | Build Runtime Context                      |
| Architect         | Produce Feature Context and Specifications |
| Planner           | Produce Implementation Plans               |
| Developer         | Implement approved Plans                   |
| Reviewer          | Validate implementation                    |

Agents never replace engineering judgement.

---

# Repository Structure

```text
.ai/
    context/
    playbooks/
    specifications/
    templates/

.github/
    agents/
    ISSUE_TEMPLATE/

```

The repository is organised around engineering knowledge rather than implementation.

---

# Human Responsibilities

Humans remain responsible for:

- Engineering decisions
- Architecture
- Production readiness
- Approval of Specifications
- Approval of Plans
- Code Review
- Deployment

AI never replaces engineering ownership.

---

# Roadmap

Version 1 focuses on GitHub Copilot and legacy application modernization.

Future versions may include:

- Additional AI runtimes
- Additional Engineering Standards
- Automated engineering metrics
- Architecture governance
- Repository bootstrap tooling

---

# Contributing

Spec-driven Development is intended to evolve through practical application.

Engineering Standards should be improved based on lessons learned from real software delivery projects.

The framework favours practical engineering experience over theoretical guidance.

---

# License

Choose an appropriate license before sharing the framework publicly.
