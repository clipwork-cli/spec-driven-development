# Oracle → PostgreSQL Migration Playbook

---

# Purpose

This playbook defines the recommended engineering workflow for migrating Oracle-backed applications to PostgreSQL.

The objective is to eliminate Oracle incrementally while preserving business behaviour, minimizing engineering risk and producing reusable engineering knowledge.

Migration should be capability-driven rather than technology-driven.

---

# Engineering Principles

Oracle → PostgreSQL migration should

- Preserve business behaviour
- Preserve runtime behaviour
- Deliver incremental value
- Minimize implementation risk
- Produce engineering evidence
- Be independently deployable

Migration is modernization.

It is not a rewrite.

---

# Migration Philosophy

Prefer

Business Capability

↓

Engineering Specification

↓

Planning

↓

Implementation

↓

Validation

↓

Merge

Avoid

Repository

↓

Schema

↓

Mass Translation

↓

Large Pull Request

↓

Big Bang Release

---

# Discovery

Migration begins only after

Repository Context

and

Runtime Context

have been completed.

Repository discovery identifies

- Oracle dependencies
- SQL usage
- Stored Procedures
- Views
- Repository boundaries

Runtime discovery identifies

- Business Capabilities
- Runtime Flows
- Runtime Dependencies
- Integration Boundaries

---

# Migration Workflow

```
Repository Discovery

↓

Repository Context

↓

Runtime Discovery

↓

Runtime Context

↓

Capability Assessment

↓

Oracle Dependency Assessment

↓

Engineering Specification

↓

Planning

↓

Implementation

↓

Validation

↓

Engineering Review

↓

Merge
```

Every migration should follow this workflow.

---

# Capability Assessment

Review every Business Capability.

Assess

- Business Value
- Runtime Isolation
- Oracle Coupling
- Shared Database Objects
- Test Coverage
- Runtime Dependencies
- Migration Readiness

Document

- Low
- Medium
- High

Migration Readiness.

---

# Selecting the Next Capability

Prefer capabilities that

- are runtime isolated
- have minimal Oracle coupling
- have good integration tests
- have limited external dependencies

Avoid highly coupled capabilities early.

Build engineering confidence first.

---

# Specification Strategy

Every Engineering Specification should represent

One Business Capability.

Example

```
CAP-001 Asset Search

↓

SPEC-001 Oracle → PostgreSQL Migration
```

Large Business Capabilities may be divided by Runtime Flow.

Never divide work by

- Repository
- Service
- Controller
- Database Object

---

# PostgreSQL Schema

The PostgreSQL schema is a required input.

Schema translation is performed outside this playbook.

The Architect should provide

- Tables
- Views
- Functions
- Indexes
- Constraints

AI consumes the translated PostgreSQL schema.

AI should not generate the target schema.

---

# Schema Context Injection

Schema inputs should be stored and referenced using these locations.

Shared schema inputs (cross-specification):

```
.ai/context/repository/database/
```

Typical files:

- schema.sql
- constraints.sql
- foreign-keys.sql
- indexes.sql
- views.sql
- functions.sql

Specification-scoped schema inputs:

```
.ai/specifications/<spec-id>/schema/
```

Use specification-scoped schema inputs for capability-specific extracts, overrides, or translation notes.

Every Specification should reference the schema inputs it consumes.

If required schema inputs are missing, report

```
Requires Human Confirmation
```

---

# Translation Strategy

Translate only the implementation required by the current Specification.

Examples

- Repository queries
- Inline SQL
- Stored Procedures
- Views
- Functions

Avoid translating unused database objects.

Migration should remain specification-scoped.

---

# Stored Procedures

Stored Procedures should be assessed individually.

Possible outcomes

- Translate to PostgreSQL Function
- Translate into application logic
- Retain temporarily
- Replace in a future Specification

The decision should preserve business behaviour.

---

# Views

Translate only the views used by the current Business Capability.

Validate

- Result sets
- Filtering
- Aggregation
- Ordering
- NULL handling

Behavioural equivalence is more important than SQL similarity.

---

# Repository Strategy

Preserve repository contracts.

Replace Oracle implementation behind existing abstractions.

Avoid changing consumers unless explicitly required.

---

# Testing Strategy

Follow

```
.ai/playbooks/oracle-to-postgresql/testing.md
```

Migration should be test-first.

Prefer

Existing Integration Tests

↓

Repository Tests

↓

Behaviour Validation

↓

Implementation

↓

Regression Validation

---

# Test Harness

Use Testcontainers where available.

Preferred

```
Testcontainers

↓

PostgreSQL

↓

Integration Tests
```

If Testcontainers are unavailable

use a local PostgreSQL Docker container.

Document local setup requirements.

---

# Validation

Every Specification should validate

✓ Business Behaviour

✓ API Contracts

✓ Runtime Behaviour

✓ Database Behaviour

✓ Integration Behaviour

✓ Operational Behaviour

Behaviour preservation is mandatory.

---

# Rollback Strategy

Every Specification should define a rollback strategy.

Examples

- Revert implementation
- Restore Oracle configuration
- Redeploy previous version

Rollback should preserve production stability.

---

# Engineering Review

Reviewer validates

- Behaviour preservation
- Translation correctness
- Engineering Standards
- Validation evidence

Reviewer should not redesign the migration.

---

# Lessons Learned

Every completed Specification should identify

- Translation improvements
- Testing improvements
- Better migration sequencing
- Common Oracle patterns
- PostgreSQL implementation guidance

Promote reusable knowledge into

- translation-rules.md
- testing.md
- Engineering Standards

---

# Definition of Done

A migration Specification is complete when

✓ Oracle dependency removed for the Business Capability

✓ PostgreSQL implementation complete

✓ Existing behaviour preserved

✓ Integration tests pass

✓ Validation evidence documented

✓ Engineering Review approved

✓ Repository Context updated (if required)

✓ Runtime Context updated (if required)

✓ Lessons Learned recorded

---

# Success Criteria

A successful Oracle → PostgreSQL migration

- removes Oracle incrementally
- preserves business behaviour
- produces independently deployable changes
- increases engineering confidence
- reduces operational risk
- improves the Engineering Standards for future migrations
