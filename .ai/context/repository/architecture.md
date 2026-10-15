# Repository Architecture

---

# Purpose

This document describes the current architecture of the repository.

Its purpose is to provide engineers and AI agents with a shared understanding of how the application is structured, how components interact, and where architectural boundaries exist.

This document describes the implementation as it exists today.

It should not describe target architecture unless explicitly stated.

---

# Scope

This document covers

- Solution architecture
- Architectural style
- Project boundaries
- Layering
- Shared libraries
- Dependency direction
- Cross-cutting concerns
- Architectural strengths
- Architectural weaknesses
- Modernization opportunities

Business behaviour is documented separately in Runtime Context.

---

# Repository Summary

## Repository

> <Repository Name>

## Primary Technology

- .NET Framework / .NET
- C#
- ASP.NET
- Angular
- SQL
- Oracle

## Repository Type

Examples

- Web Application
- API
- Worker
- Library
- Desktop Application

---

# Architectural Style

Identify the dominant architecture.

Examples

- Layered Architecture
- Clean Architecture
- Onion Architecture
- Vertical Slice
- Domain Driven Design
- MVC
- Modular Monolith

If multiple styles exist

document each.

---

# Solution Structure

Describe the solution structure.

Example

```
src/

tests/

docs/

scripts/

build/
```

Describe the purpose of each top-level directory.

---

# Project Structure

Summarise each project.

For every project document

- Purpose
- Responsibilities
- Dependencies
- Consumers

Example

| Project  | Purpose         | Depends On |
| -------- | --------------- | ---------- |
| API      | HTTP endpoints  | Services   |
| Services | Business logic  | Data       |
| Data     | Database access | Oracle     |

---

# Layering

Describe repository layers.

Examples

Presentation

↓

Application

↓

Domain

↓

Infrastructure

↓

Database

Identify deviations from the intended layering.

---

# Dependency Rules

Document dependency direction.

Examples

Presentation

→ Application

Application

→ Domain

Infrastructure

→ External Systems

Identify dependency violations.

---

# Shared Libraries

Document shared libraries.

For each shared library include

- Purpose
- Consumers
- Coupling
- Reusability

Identify opportunities for consolidation.

---

# Cross-Cutting Concerns

Document

- Logging
- Authentication
- Authorization
- Configuration
- Dependency Injection
- Validation
- Caching
- Messaging

Describe how each concern is implemented.

---

# External Dependencies

Identify external systems.

Examples

- Oracle
- PostgreSQL
- Azure
- Kafka
- REST APIs
- Storage
- Active Directory

Document

- Usage
- Criticality
- Coupling

---

# Architectural Findings

Summarise important observations.

Examples

- Strong separation of concerns.
- High coupling between Services and Data.
- Shared library reused across unrelated domains.
- Repository follows layered architecture.
- Circular project references detected.

Focus on observations rather than recommendations.

---

# Architectural Risks

Document architectural risks.

Examples

- Tight coupling
- Circular dependencies
- Obsolete frameworks
- Unsupported packages
- Shared mutable state
- Large God classes
- Monolithic services

Classify

Low

Medium

High

---

# Modernization Opportunities

Identify opportunities that do not require business behaviour changes.

Examples

- Upgrade to .NET Framework 4.8
- Replace deprecated NuGet packages
- Remove obsolete APIs
- Enable nullable reference types
- Improve dependency injection
- Remove dead code

These are observations only.

Do not produce implementation plans.

---

# Assumptions

Document assumptions made during discovery.

Examples

- Layer boundaries inferred from project references.
- Build configuration not verified.
- Runtime behaviour inferred from source code.

If uncertain

record

```
Requires Human Confirmation
```

---

# References

Reference supporting documentation.

Examples

- repository.md
- dependencies.md
- projects.md
- build.md

---

# Last Generated

Date

Repository Commit

Generator

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

Rate confidence in the findings.

High

Repository fully analysed.

Medium

Most architectural patterns identified.

Low

Repository partially analysed.

Include reasons for reduced confidence where applicable.

---

# Success Criteria

This document is complete when

✓ Architectural style identified

✓ Solution structure documented

✓ Project boundaries documented

✓ Dependency rules documented

✓ Shared libraries documented

✓ Cross-cutting concerns documented

✓ External dependencies documented

✓ Architectural findings recorded

✓ Architectural risks identified

✓ Modernization opportunities documented

✓ Assumptions recorded

✓ Confidence assessed
