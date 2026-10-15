# Repository Context

Repository Context describes the long-lived engineering knowledge of a repository.

Repository Context should answer

> "How is this repository built?"

It should not describe

- business processes
- runtime behaviour
- individual features

Those belong in Runtime Context.

---

# Purpose

Repository Context provides a stable engineering baseline that every AI agent can reuse.

The objective is to eliminate repeated repository discovery.

Repository Context should evolve as the repository evolves.

---

# Repository Context Structure

```
architecture.md

repository.md

projects.md

dependencies.md

database.md

testing.md

build.md

modernization.md

risks.md

database/
```

`database/` is optional and is used for shared schema input artifacts (for example schema.sql, constraints.sql, foreign-keys.sql, indexes.sql) that specifications may reference.

---

# Documents

## architecture.md

Overall repository architecture.

Examples

- Architectural Style
- Layers
- Shared Libraries
- Solution Structure
- Repository Boundaries

---

## repository.md

General repository information.

Examples

- Solution Layout
- Programming Languages
- Framework Versions
- Technology Stack

---

## projects.md

Individual projects.

Examples

- APIs
- Libraries
- Workers
- Test Projects

Project relationships.

---

## dependencies.md

Repository dependencies.

Examples

- NuGet Packages
- Internal Libraries
- External Systems

Dependency ownership.

---

## database.md

Repository database usage.

Examples

- Oracle
- PostgreSQL
- SQL Server

Repositories

ORM

Stored Procedures

Views

Functions

Sequences

---

## testing.md

Repository testing strategy.

Examples

- Unit Tests

- Integration Tests

- Testcontainers

- Mocking

- Code Coverage

---

## build.md

Repository build process.

Examples

- Build

- CI

- CD

- GitHub Actions

- Azure DevOps

---

## modernization.md

Repository modernization opportunities.

Examples

- Framework upgrades

- Package upgrades

- Deprecated APIs

- Security

- Technical Debt

---

## risks.md

Repository-level engineering risks.

Examples

- Legacy frameworks

- Unsupported dependencies

- Large projects

- High coupling

- Build instability

---

# Ownership

Repository Context is owned by

Static Discovery.

Repository Context should only change when repository knowledge changes.

Feature work should not modify Repository Context unless repository behaviour has changed.

---

# Consumers

Repository Context is consumed by

- Architect

- Planner

- Developer

- Reviewer

Repository Context should be considered read-only during feature implementation.

---

# Success Criteria

Repository Context is complete when

✓ Repository architecture documented

✓ Projects documented

✓ Dependencies documented

✓ Database usage documented

✓ Testing documented

✓ Build process documented

✓ Modernization opportunities documented

✓ Repository risks documented
