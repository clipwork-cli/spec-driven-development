# Projects

---

# Purpose

This document describes every project within the repository.

Its purpose is to provide engineers and AI agents with a complete inventory of the repository structure, project responsibilities and project relationships.

Projects are the primary structural units of the repository.

This document should answer

> "What projects exist and what is each responsible for?"

---

# Scope

This document covers

- Projects
- Responsibilities
- Dependencies
- Project relationships
- Entry points
- Shared libraries
- Test projects
- Project health

This document does not describe runtime behaviour.

---

# Repository Summary

## Total Projects

Document

- Production Projects
- Test Projects
- Shared Libraries
- Samples
- Tools

---

## Solution Structure

Document

- Solution files
- Project folders
- Project grouping

Example

```
src/

tests/

tools/

samples/
```

---

# Project Inventory

Document every project.

Use the following structure.

---

## Project

### Name

```
Example.Api
```

### Path

```
src/Example.Api
```

### Type

Examples

- ASP.NET API
- Class Library
- Worker Service
- Console
- Test Project

### Purpose

Describe the responsibility of the project.

### Entry Points

Examples

- Controllers
- Background Jobs
- Hosted Services
- Queue Consumers

### Dependencies

Document

- Internal project references
- External packages
- Infrastructure dependencies

### Consumers

Document which projects reference this project.

### Database Usage

Examples

- Oracle
- PostgreSQL
- SQL Server

If none

record

```
None
```

### Testing

Document associated test projects.

### Ownership

If known

document ownership.

Otherwise

```
Unknown
```

---

# Project Relationships

Describe dependency direction.

Example

```
API

↓

Application

↓

Domain

↓

Infrastructure
```

Document dependency violations.

---

# Shared Libraries

Document reusable libraries.

For every library include

- Purpose
- Consumers
- Coupling
- Reuse opportunities

Identify libraries with excessive responsibilities.

---

# Entry Points

Identify repository entry points.

Examples

- APIs
- Controllers
- Workers
- Queue Consumers
- Scheduled Jobs
- Azure Functions

These entry points are later used during Runtime Discovery.

---

# Test Projects

Document

- Test Framework
- Coverage Scope
- Integration Tests
- Unit Tests
- End-to-End Tests

Identify projects with no associated tests.

---

# Facts

Record verified facts.

Examples

- Repository contains 22 projects.
- Four ASP.NET APIs.
- Eight shared libraries.
- Six test projects.
- One Windows Service.

Facts should be directly observable.

---

# Observations

Document engineering observations.

Examples

- Infrastructure shared across unrelated domains.
- API projects duplicate configuration.
- Test coverage inconsistent.
- Large shared utility library.

Observations are engineering interpretations.

---

# Recommendations

Recommend repository improvements.

Examples

- Split oversized shared library.
- Consolidate duplicate infrastructure.
- Introduce project conventions.
- Add missing test projects.

Recommendations should preserve repository behaviour.

---

# Risks

Identify project-level engineering risks.

Examples

- Circular project references
- Obsolete project types
- Unsupported frameworks
- Large project coupling
- Missing test coverage

Classify

Low

Medium

High

---

# Questions Raised

Examples

- Is this project still actively used?
- Can this shared library be decomposed?
- Should this project be archived?
- Are duplicate APIs intentional?

---

# Assumptions

Document assumptions made during discovery.

Examples

- Unreferenced projects assumed inactive.
- Legacy projects assumed production unless excluded.

If uncertain

record

```
Requires Human Confirmation
```

---

# References

Reference related documents.

Examples

- repository.md
- architecture.md
- dependencies.md
- database.md

---

# Last Generated

Document

- Generation date
- Repository commit
- Generator

Example

```
Generated

2026-07-15

Commit

abc1234

Generator

Static Discovery Agent v1.0
```

---

# Confidence

Rate confidence

High

Medium

Low

Explain any uncertainty.

---

# Success Criteria

This document is complete when

✓ Every project identified

✓ Every project classified

✓ Responsibilities documented

✓ Dependencies documented

✓ Entry points documented

✓ Test projects documented

✓ Shared libraries documented

✓ Facts recorded

✓ Observations recorded

✓ Recommendations recorded

✓ Risks identified

✓ Questions Raised documented

✓ Assumptions documented

✓ Confidence assessed
