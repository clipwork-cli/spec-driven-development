# Repository Overview

---

# Purpose

This document provides a high-level overview of the repository.

It describes what the repository contains, the technologies it uses, its primary responsibilities, and its overall engineering characteristics.

This document should enable a new engineer or AI agent to quickly understand the repository before examining implementation details.

---

# Scope

This document covers

- Repository purpose
- Technology stack
- Solution layout
- Programming languages
- Frameworks
- Build system
- Package management
- Repository statistics
- Ownership
- Engineering characteristics

It does not describe runtime behaviour or business capabilities.

---

# Repository Summary

## Repository Name

> <Repository Name>

## Description

Provide a concise description of the repository's purpose.

Example

> Backend services supporting the Ravnen application for asset operations.

---

## Repository Type

Examples

- Web Application
- REST API
- Background Worker
- Desktop Application
- Shared Library
- Full Stack
- Monorepo

---

## Primary Language(s)

Examples

- C#
- TypeScript
- SQL
- PowerShell

---

## Primary Framework(s)

Examples

- .NET Framework 4.7.2
- ASP.NET MVC
- Angular 16

---

## Repository Size

Document

- Number of projects
- Number of solutions
- Estimated source files
- Estimated test files

These values are approximate.

---

# Technology Stack

Summarise the technologies used.

## Backend

Examples

- ASP.NET
- Web API
- WCF
- Windows Service

---

## Frontend

Examples

- Angular
- React
- Razor
- Blazor

---

## Database

Examples

- Oracle
- PostgreSQL
- SQL Server

---

## Messaging

Examples

- Kafka
- RabbitMQ
- Azure Service Bus

---

## Storage

Examples

- Azure Blob Storage
- File System
- S3

---

## Authentication

Examples

- Active Directory
- Azure AD
- OAuth2
- JWT

---

## Logging

Examples

- Serilog
- NLog
- log4net

---

## Testing

Examples

- xUnit
- NUnit
- MSTest

---

# Repository Layout

Describe the top-level directory structure.

Example

```
src/

tests/

scripts/

docs/

build/
```

Document the purpose of each directory.

---

# Build System

Document

- Solution files
- Build tooling
- Package manager
- Build scripts
- CI platform

Examples

- MSBuild
- dotnet CLI
- NuGet
- GitHub Actions
- Azure DevOps

---

# Engineering Characteristics

Document notable repository characteristics.

Examples

- Large monolith
- Layered architecture
- Multiple entry points
- Shared infrastructure
- Legacy components
- High coupling
- Extensive SQL usage

Focus on facts.

---

# Facts

Record verified repository facts.

Examples

- Targets .NET Framework 4.7.2
- Uses Oracle.ManagedDataAccess
- Contains 18 projects
- Uses Autofac for dependency injection
- Uses Dapper for data access

Facts should be directly observable from the repository.

---

# Observations

Document engineering observations.

Examples

- Strong separation between API and Services.
- Oracle usage concentrated in Infrastructure.
- Tests cover only repository layer.
- Build scripts are duplicated.

Observations are engineering interpretations based on facts.

---

# Recommendations

Recommend improvements.

Examples

- Upgrade to .NET Framework 4.8.
- Consolidate build scripts.
- Centralise package versions.
- Isolate Oracle dependencies.

Recommendations should not redefine architecture.

---

# Assumptions

Document assumptions made during repository discovery.

Examples

- Solution file appears complete.
- Build scripts were not executed.
- Local development environment not validated.

If uncertain

record

```
Requires Human Confirmation
```

---

# References

Reference related Repository Context documents.

Examples

- architecture.md
- projects.md
- dependencies.md
- build.md

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

Explain factors that reduced confidence.

---

# Success Criteria

This document is complete when

✓ Repository purpose documented

✓ Technology stack documented

✓ Repository layout documented

✓ Build system documented

✓ Engineering characteristics documented

✓ Facts recorded

✓ Observations recorded

✓ Recommendations documented

✓ Assumptions recorded

✓ Confidence assessed
