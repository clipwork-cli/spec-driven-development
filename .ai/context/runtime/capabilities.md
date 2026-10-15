# Business Capabilities

---

# Purpose

This document identifies the Business Capabilities supported by the application.

Its purpose is to provide architects and AI agents with a capability-centric view of the system.

Business Capabilities are the primary units used to generate Engineering Specifications.

This document should answer

> "What business capabilities does this application provide?"

Business Capabilities are independent of repository structure.

They describe business value rather than technical implementation.

---

# Scope

This document covers

- Business Capabilities
- Capability responsibilities
- Capability boundaries
- Capability ownership
- Runtime entry points
- Database dependencies
- External integrations
- Runtime dependencies

Implementation details belong elsewhere.

---

# Capability Summary

Document

- Total Business Capabilities
- Major Domains
- Shared Capabilities
- Cross-Cutting Capabilities

Example

```
17 Business Capabilities

3 Shared Capabilities

2 Cross-Cutting Capabilities
```

---

# Capability Inventory

Document every Business Capability.

Use the following structure.

---

## Capability

### Name

```
Asset Search
```

---

### Business Objective

Describe the business outcome.

Example

> Allow operators to search assets using multiple search criteria.

---

### Business Value

Describe why the capability exists.

Focus on business value rather than implementation.

---

### Runtime Entry Points

Examples

- Controllers
- APIs
- Queue Consumers
- Scheduled Jobs
- Background Workers

Reference

```
entry-points.md
```

where appropriate.

---

### Primary Components

Document major implementation components.

Examples

- Controllers
- Services
- Repositories
- Validators
- Handlers

---

### Database Objects

Document

- Tables
- Views
- Stored Procedures
- Functions
- Sequences

Reference

```
repository/database.md
```

Do not duplicate discovery results.

---

### External Integrations

Examples

- SAP
- Oracle
- Kafka
- REST APIs

---

### Runtime Dependencies

Document dependencies on other capabilities.

Examples

Authentication

↓

Asset Search

↓

Reporting

Document only runtime dependencies.

---

### Cross-Cutting Concerns

Examples

- Authorization
- Logging
- Validation
- Auditing

---

### Engineering Standards

Identify Engineering Standards likely to apply.

Examples

- Oracle → PostgreSQL
- Modernization
- Testcontainers

---

### Complexity

Classify

- Low
- Medium
- High

Complexity reflects engineering effort.

Not business importance.

---

### Migration Readiness

Assess

- Low
- Medium
- High

Consider

- Oracle coupling
- Test coverage
- Runtime isolation
- Repository isolation

---

### Testability

Assess

- Existing Unit Tests
- Integration Tests
- Feature Tests
- Manual Validation

Document confidence.

---

### Manual Activities

Examples

- PostgreSQL schema translation
- Data migration
- Business validation

---

# Capability Relationships

Document runtime relationships.

Example

```
Authentication

↓

Asset Search

↓

Reporting
```

Avoid implementation detail.

Focus on business dependency.

---

# Candidate Engineering Specifications

Recommend logical Specification boundaries.

Examples

Specification 1

Asset Search

Specification 2

Reporting

Specification 3

Inspection History

Specifications should preserve Business Capability boundaries.

Avoid splitting capabilities across multiple Specifications unless complexity requires it.

---

# Facts

Record verified facts.

Examples

- Asset Search uses five repositories.
- Reporting depends on Oracle views.
- Synchronization uses Kafka.

Facts should be directly observable.

---

# Observations

Document engineering observations.

Examples

- Asset Search largely isolated.
- Reporting tightly coupled to Oracle.
- Authentication shared by all capabilities.

---

# Recommendations

Recommend Specification boundaries.

Examples

- Asset Search can migrate independently.
- Reporting should be split into two Specifications.
- Authentication should remain unchanged.

Recommendations should preserve business behaviour.

---

# Risks

Examples

- Shared repositories
- Shared stored procedures
- Cross-capability transactions
- Tight Oracle coupling

Classify

Low

Medium

High

---

# Questions Raised

Examples

- Can Reporting be isolated?
- Can Asset Search migrate independently?
- Which capabilities share Oracle packages?
- Which capability should migrate first?

---

# Assumptions

Document assumptions made during discovery.

Examples

- Capability boundaries inferred from runtime entry points.
- Business ownership unavailable.
- Runtime flows partially inferred.

If uncertain

```
Requires Human Confirmation
```

---

# References

Repository Context

- projects.md
- entry-points.md
- dependencies.md
- database.md

Runtime Context

- runtime-flow.md
- operations.md

---

# Last Generated

Document

- Generation Date
- Repository Commit
- Generator

---

# Confidence

High

Medium

Low

Explain uncertainty.

---

# Success Criteria

✓ Business Capabilities identified

✓ Capability boundaries documented

✓ Runtime entry points identified

✓ Runtime dependencies documented

✓ Database dependencies referenced

✓ External integrations documented

✓ Migration readiness assessed

✓ Testability assessed

✓ Candidate Specification boundaries identified

✓ Facts recorded

✓ Observations recorded

✓ Recommendations recorded

✓ Risks documented

✓ Questions Raised documented

✓ Assumptions documented

✓ Confidence assessed
