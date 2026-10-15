# Dependencies

---

# Purpose

This document describes the dependencies within and outside the repository.

Its purpose is to provide engineers and AI agents with a clear understanding of how projects depend on each other, what external technologies are required, and where coupling exists.

This document should answer

> "What does this repository depend on?"

It should not describe runtime behaviour.

---

# Scope

This document covers

- Project dependencies
- External dependencies
- Framework dependencies
- Package dependencies
- Infrastructure dependencies
- Database dependencies
- Service dependencies
- Messaging dependencies

---

# Dependency Summary

Document

- Internal project references
- External packages
- Infrastructure dependencies
- External systems
- Third-party services

---

# Internal Dependencies

Document project-to-project dependencies.

Use the following structure.

## Project

### Name

```
Example.Api
```

### Depends On

Examples

- Application
- Infrastructure
- Shared

### Used By

Examples

- Web
- Worker

### Dependency Direction

Document whether dependency direction follows architectural rules.

---

# External Packages

Document significant packages.

Ignore trivial libraries.

For each package include

- Name
- Version
- Purpose
- Projects
- Criticality

Examples

- Oracle.ManagedDataAccess
- Dapper
- Autofac
- Serilog

---

# Framework Dependencies

Document

- Target Framework
- SDK
- Runtime

Examples

- .NET Framework 4.7.2
- .NET 8
- ASP.NET MVC

---

# Infrastructure Dependencies

Document

- Database
- Storage
- Cache
- Messaging
- Identity
- Configuration

Examples

- Oracle
- Redis
- Kafka
- Azure Service Bus
- Active Directory

---

# External Systems

Document integrations.

Examples

- SAP
- Salesforce
- Azure
- Internal REST APIs
- SOAP Services

For each system record

- Purpose
- Consumers
- Criticality

---

# Database Dependencies

Summarise

- Oracle client usage
- PostgreSQL client usage
- SQL Server usage

Reference

```
database.md
```

for detailed analysis.

---

# Messaging Dependencies

Document

- Kafka
- Azure Service Bus
- RabbitMQ
- Event Grid

Describe

- producers
- consumers
- shared libraries

---

# Configuration Dependencies

Document

- app.config
- web.config
- appsettings.json
- environment variables
- secrets

---

# Build Dependencies

Document

- NuGet feeds
- Build tools
- SDK requirements

Reference

```
build.md
```

for implementation details.

---

# Facts

Examples

- Oracle.ManagedDataAccess referenced by five projects.
- Autofac used across the solution.
- Serilog configured centrally.
- Dapper used by Infrastructure.

Facts should be directly observable.

---

# Observations

Examples

- Oracle dependency isolated to Infrastructure.
- Logging implementation inconsistent.
- Multiple projects duplicate package references.
- High coupling to internal shared library.

---

# Recommendations

Examples

- Centralise package versions.
- Remove obsolete packages.
- Reduce shared library coupling.
- Upgrade unsupported packages.

Recommendations should preserve repository behaviour.

---

# Risks

Examples

- Unsupported packages
- Circular project references
- Tight external coupling
- Obsolete frameworks
- Single points of failure

Classify

Low

Medium

High

---

# Questions Raised

Examples

- Can Oracle.ManagedDataAccess be isolated further?
- Which external APIs are business critical?
- Can package versions be centralised?
- Are all messaging integrations still active?

---

# Assumptions

Document assumptions.

If uncertain

```
Requires Human Confirmation
```

---

# References

Related Repository Context

- repository.md
- architecture.md
- projects.md
- database.md
- build.md

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

✓ Internal dependencies documented

✓ External packages documented

✓ Framework dependencies documented

✓ Infrastructure dependencies documented

✓ External systems documented

✓ Messaging dependencies documented

✓ Configuration dependencies documented

✓ Facts recorded

✓ Observations recorded

✓ Recommendations recorded

✓ Risks documented

✓ Questions Raised documented

✓ Assumptions documented

✓ Confidence assessed
