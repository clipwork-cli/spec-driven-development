# Engineering Specifications

---

# Purpose

Engineering Specifications define repository-specific engineering work.

A Specification represents one independently deliverable engineering change.

Specifications are generated after Repository Context and Runtime Context have been completed.

Specifications are owned by the Architect.

---

# Engineering Lifecycle

Specifications are created after Discovery.

```
Repository Context

↓

Runtime Context

↓

Capability Assessment

↓

Specification Candidate

↓

Architect Approval

↓

Engineering Specification

↓

Planning

↓

Implementation

↓

Engineering Review

↓

Validation
```

Specifications should never be generated without Repository Context and Runtime Context.

---

# Directory Structure

```
.ai/specifications/

README.md

SPEC-001/

    specification.md

    plan.md

    tasks.md

    review.md

    validation.md
```

Additional supporting documentation may be added where appropriate.

Examples

```
analysis.md

notes.md

migration.md
```

These are optional.

For Oracle → PostgreSQL specifications, a schema input directory may also be added:

```
schema/
```

Use this for capability-specific schema artifacts referenced by the specification.

---

# Specification Ownership

Each artifact has one owner.

| Artifact         | Owner                |
| ---------------- | -------------------- |
| specification.md | Architect            |
| plan.md          | Planner              |
| tasks.md         | Developer            |
| review.md        | Reviewer             |
| validation.md    | Developer + Reviewer |

Ownership should remain clear throughout implementation.

---

# Specification Principles

Every Specification should

- preserve business behaviour
- deliver business value
- be independently testable
- minimise implementation risk
- minimise repository coupling
- maximise traceability

Specifications should describe

what

not

how.

Implementation belongs to Planning.

---

# Specification Scope

Specifications should normally represent one Business Capability.

Examples

```
CAP-001 Asset Search

↓

SPEC-001 Asset Search Migration
```

Large capabilities may be divided into multiple Specifications.

Examples

```
CAP-010 Reporting

↓

SPEC-010 Reporting Queries

SPEC-011 Reporting Views

SPEC-012 Reporting Export
```

Every Specification should remain independently deliverable.

---

# Specification Inputs

Architect should use

Repository Context

```
.ai/context/repository/
```

Runtime Context

```
.ai/context/runtime/
```

Engineering Standards

```
.ai/playbooks/
```

Discovery Findings

Business Capability Assessment

Migration Readiness

Repository Risks

Runtime Risks

Specifications should be evidence-driven.

---

# Specification Deliverables

Every Specification directory contains

```
specification.md

plan.md

tasks.md

review.md

validation.md
```

Purpose

| Document         | Purpose                     |
| ---------------- | --------------------------- |
| specification.md | Engineering scope           |
| plan.md          | Implementation strategy     |
| tasks.md         | Engineering tasks           |
| review.md        | Engineering review findings |
| validation.md    | Engineering evidence        |

---

# Engineering Standards

Specifications reference Engineering Standards.

Examples

- Oracle → PostgreSQL
- Modernization
- Test Harness
- Coding Standards

Engineering Standards define

how

implementation should be performed.

Specifications define

what

should be implemented.

---

# Repository Context

Specifications should reference Repository Context.

Examples

- Architecture
- Dependencies
- Database
- Testing
- Modernization

Repository Context provides engineering knowledge.

---

# Runtime Context

Specifications should reference Runtime Context.

Examples

- Business Capability
- Runtime Flow
- Integrations
- Operations
- Data Flow

Runtime Context provides behavioural knowledge.

---

# Specification Traceability

Every Specification should be traceable.

```
Business Capability

↓

Repository Context

↓

Runtime Context

↓

Specification

↓

Plan

↓

Tasks

↓

Implementation

↓

Review

↓

Validation
```

Traceability should be maintained throughout implementation.

---

# Completion Criteria

A Specification is complete when

✓ Specification approved

✓ Plan approved

✓ Tasks completed

✓ Engineering Review completed

✓ Validation completed

✓ Applicable Engineering Standards satisfied

✓ Business behaviour preserved

✓ Documentation updated

---

# Success Criteria

Engineering Specifications should

- preserve business behaviour
- minimise implementation risk
- maximise engineering traceability
- support incremental delivery
- support independent deployment
- provide sufficient engineering evidence
- enable reuse across repositories
