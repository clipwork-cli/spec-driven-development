# Repository Risk Assessment

---

# Purpose

This document identifies engineering risks within the repository.

Its purpose is to help engineers, architects and AI agents understand which parts of the repository require additional care during planning and implementation.

This document should answer

> "What engineering risks exist within this repository?"

This document is not a project risk register.

---

# Scope

This document covers

- Architectural risks
- Technical risks
- Repository risks
- Dependency risks
- Database risks
- Build risks
- Testing risks
- Operational risks

Business risks are out of scope.

---

# Risk Summary

Summarise the overall engineering health of the repository.

Example

Overall Risk

Medium

Primary Drivers

- Legacy framework
- Oracle dependency
- Limited integration testing

---

# Risk Register

Document every significant engineering risk.

---

## Risk

### Identifier

```
RISK-001
```

---

### Title

Short description.

Example

```
Strong Oracle Coupling
```

---

### Category

Examples

- Architecture
- Database
- Dependencies
- Build
- Testing
- Security
- Maintainability
- Performance
- Operations

---

### Description

Describe the risk.

---

### Evidence

Reference supporting facts.

Example

- Oracle.ManagedDataAccess referenced by six projects.
- 47 OracleConnection usages detected.

Evidence should come from Repository Context.

---

### Impact

Describe the engineering impact.

Examples

- Increased migration effort
- Difficult testing
- Build instability
- Increased review effort

---

### Likelihood

Classify

- Low
- Medium
- High

---

### Severity

Classify

- Low
- Medium
- High
- Critical

---

### Affected Components

Document affected

- Projects
- Libraries
- Database
- External Systems

---

### Recommended Mitigation

Describe possible mitigation.

Do not produce implementation plans.

Examples

- Isolate Oracle access.
- Upgrade framework.
- Improve integration testing.

---

### Related Documents

Examples

- architecture.md
- database.md
- modernization.md

---

# Architectural Risks

Examples

- High coupling
- Circular dependencies
- God services
- Layer violations

---

# Database Risks

Examples

- Oracle-specific SQL
- Dynamic SQL
- Heavy Stored Procedure usage
- Mixed transaction patterns

---

# Dependency Risks

Examples

- Unsupported NuGet packages
- Duplicate package versions
- Shared libraries with excessive responsibility

---

# Build Risks

Examples

- Legacy SDK
- Manual build steps
- Inconsistent build environments
- Build script duplication

---

# Testing Risks

Examples

- Missing integration tests
- Shared databases
- Weak regression coverage
- Slow test execution

---

# Security Risks

Examples

- Deprecated libraries
- Hardcoded configuration
- Legacy authentication
- Missing secret management

This document is not a security assessment.

---

# Operational Risks

Examples

- Manual deployment
- Missing monitoring
- Missing health checks
- Limited observability

---

# Risk Hotspots

Identify areas where multiple risks overlap.

Examples

Infrastructure project

- Oracle dependency
- High coupling
- Missing tests

Reporting module

- Dynamic SQL
- Stored Procedures
- Legacy framework

These hotspots should receive additional engineering attention.

---

# Facts

Record verified facts supporting identified risks.

Facts should be directly observable.

---

# Observations

Document engineering observations.

Examples

- Most risks concentrated within Infrastructure.
- Build risks relatively low.
- Oracle risks isolated.

---

# Recommendations

Recommend engineering improvements.

Examples

- Upgrade .NET Framework before Oracle migration.
- Improve integration testing.
- Consolidate package versions.

Recommendations should preserve repository behaviour.

---

# Questions Raised

Examples

- Can Oracle dependency be isolated further?
- Which risks should be addressed before modernization?
- Are current tests sufficient for migration?

---

# Assumptions

Document assumptions made during assessment.

If uncertain

```
Requires Human Confirmation
```

---

# References

Related Repository Context

- architecture.md
- dependencies.md
- database.md
- modernization.md
- testing.md

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

✓ Architectural risks identified

✓ Database risks identified

✓ Dependency risks identified

✓ Build risks identified

✓ Testing risks identified

✓ Operational risks identified

✓ Risk hotspots identified

✓ Evidence documented

✓ Recommendations recorded

✓ Questions Raised documented

✓ Assumptions documented

✓ Confidence assessed
