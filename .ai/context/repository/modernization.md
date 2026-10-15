# Modernization Assessment

---

# Purpose

This document identifies opportunities to modernize the repository while preserving existing business behaviour.

Its purpose is to provide architects and AI agents with an engineering assessment of the repository's technical health.

This document should answer

> "What engineering improvements are possible without changing business functionality?"

It should not contain implementation plans.

Implementation planning belongs to the Planner.

---

# Scope

This document covers

- Framework modernization
- Package modernization
- Language modernization
- Build modernization
- Testing improvements
- Dependency improvements
- Security improvements
- Engineering debt

This document does not recommend architectural redesign.

---

# Modernization Summary

Summarise the overall modernization state.

Examples

- Legacy
- Partially Modernized
- Modern
- Actively Maintained

Include a brief explanation.

---

# Framework Assessment

Document

- Current Framework
- Latest Supported Version
- Upgrade Readiness
- Compatibility Risks

Examples

.NET Framework 4.7.2

↓

.NET Framework 4.8

Compatibility

Low Risk

---

# Package Assessment

Identify outdated packages.

For each package include

- Package Name
- Current Version
- Latest Stable Version
- Upgrade Risk
- Notes

Ignore insignificant packages.

Focus on engineering impact.

---

# Language Features

Assess usage of modern language features.

Examples

- Nullable Reference Types
- Records
- Pattern Matching
- Async/Await
- Global Using
- File Scoped Namespaces

Document opportunities for improvement.

---

# Dependency Assessment

Assess

- Shared Libraries
- Circular Dependencies
- Tight Coupling
- Obsolete Libraries
- Duplicate Dependencies

Reference

```
dependencies.md
```

where appropriate.

---

# Database Modernization

Assess

- Oracle coupling
- SQL portability
- Repository abstraction
- Transaction strategy
- ORM usage

Reference

```
database.md
```

Do not duplicate findings.

---

# Build Modernization

Assess

- Build tooling
- SDK versions
- CI maturity
- Package management
- Automation

Reference

```
build.md
```

---

# Testing Modernization

Assess

- Unit test quality
- Integration testing
- Testcontainers adoption
- Test isolation
- Coverage maturity

Reference

```
testing.md
```

---

# Security Assessment

Identify engineering improvements.

Examples

- Deprecated libraries
- Vulnerable packages
- Configuration issues
- Secret management
- Authentication improvements

Do not perform security audits.

---

# Engineering Debt

Document significant technical debt.

Examples

- God classes
- Duplicate code
- Large repositories
- Legacy APIs
- Dead code
- Manual processes

Focus on engineering impact.

---

# Quick Wins

Identify low-risk improvements.

Examples

- Upgrade to .NET Framework 4.8
- Remove deprecated packages
- Centralize package versions
- Remove unused references
- Replace obsolete APIs

Quick wins should

- preserve behaviour
- require minimal validation
- reduce future engineering effort

---

# Modernization Candidates

Identify larger engineering initiatives.

Examples

- Oracle → PostgreSQL
- .NET Framework → .NET 8
- Dependency Injection modernization
- Logging standardization
- Build modernization

These are observations only.

Do not produce implementation plans.

---

# Facts

Examples

- Repository targets .NET Framework 4.7.2.
- Oracle.ManagedDataAccess referenced by six projects.
- 43 outdated NuGet packages detected.

Facts should be directly observable.

---

# Observations

Examples

- Framework upgrade appears low risk.
- Oracle usage isolated to Infrastructure.
- Package versions inconsistent.
- Test infrastructure outdated.

Observations should be supported by facts.

---

# Recommendations

Recommend modernization opportunities.

Examples

- Upgrade to .NET Framework 4.8 before Oracle migration.
- Consolidate package versions.
- Introduce Testcontainers.
- Remove obsolete APIs.

Recommendations should preserve repository behaviour.

---

# Risks

Examples

- Unsupported framework
- End-of-life packages
- Legacy authentication
- Tight Oracle coupling
- Build instability

Classify

- Low
- Medium
- High

---

# Questions Raised

Examples

- Can framework upgrades be completed independently?
- Are all Oracle APIs still required?
- Can package upgrades be automated?
- Which modernization should happen first?

---

# Assumptions

Document assumptions.

Examples

- Compatibility not validated.
- Package upgrades inferred.
- Framework support assumed.

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
- build.md
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

✓ Framework assessed

✓ Packages assessed

✓ Language features assessed

✓ Dependencies assessed

✓ Database modernization assessed

✓ Build modernization assessed

✓ Testing modernization assessed

✓ Security improvements identified

✓ Engineering debt documented

✓ Quick wins identified

✓ Modernization candidates identified

✓ Facts recorded

✓ Observations recorded

✓ Recommendations recorded

✓ Risks documented

✓ Questions Raised documented

✓ Assumptions documented

✓ Confidence assessed
