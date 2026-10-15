# Testing

---

# Purpose

This document describes the repository's engineering validation strategy.

Its purpose is to help engineers and AI agents understand how repository changes are verified before implementation is accepted.

This document should answer

> "How do we prove repository behaviour is preserved?"

Testing is only one form of validation.

---

# Scope

This document covers

- Testing strategy
- Test frameworks
- Test projects
- Test execution
- Test infrastructure
- Integration testing
- Test data
- Coverage
- Engineering validation

This document does not describe business acceptance testing.

---

# Validation Philosophy

Describe how engineering changes are validated.

Examples

- Unit Testing
- Integration Testing
- Feature Testing
- Regression Testing
- Manual Validation

Validation should provide evidence that repository behaviour has been preserved.

---

# Testing Summary

Document

- Test Framework(s)
- Test Projects
- Integration Tests
- Test Harnesses
- Test Infrastructure
- Code Coverage (if available)

---

# Test Projects

Document every test project.

For each project include

## Project

Name

Purpose

Framework

Target Project

Execution Method

Coverage Scope

---

# Test Frameworks

Examples

- xUnit
- NUnit
- MSTest
- Playwright
- Cypress

Document where each framework is used.

---

# Test Types

Document supported test types.

Examples

## Unit Tests

Purpose

Scope

Execution

---

## Integration Tests

Purpose

Scope

Dependencies

---

## Feature Tests

Purpose

Business Capability Coverage

---

## Regression Tests

Purpose

Execution Frequency

---

## Manual Validation

Purpose

Owner

---

# Test Infrastructure

Document supporting infrastructure.

Examples

- Testcontainers
- Docker
- Local PostgreSQL
- Local SQL Server
- Mock Services
- WireMock

Describe how infrastructure is provisioned.

---

# Database Testing

Document

- Database reset strategy
- Seed data
- Test schema
- Transaction rollback
- Isolation

For Oracle → PostgreSQL migrations

document

- PostgreSQL Testcontainers support
- Local Docker fallback
- Schema loading process

---

# Test Harness

Describe reusable testing utilities.

Examples

- Base integration tests
- Test fixtures
- Test data builders
- Mock factories
- Shared assertions

Identify opportunities to improve reuse.

---

# Test Execution

Document the canonical workflow.

Example

```
Restore

↓

Build

↓

Unit Tests

↓

Integration Tests

↓

Feature Validation
```

---

# Engineering Validation

Document the minimum validation required before a Pull Request.

Examples

✓ Build succeeds

✓ Unit Tests pass

✓ Integration Tests pass

✓ No regression failures

✓ Manual validation completed (if required)

---

# Facts

Examples

- Repository contains 320 unit tests.
- Integration tests use Testcontainers.
- PostgreSQL container starts automatically.
- Test data seeded before execution.

Facts should be directly observable.

---

# Observations

Examples

- Integration coverage is strong.
- Database tests are slow.
- Feature tests missing.
- Manual validation required for reporting.

---

# Recommendations

Examples

- Increase feature-level testing.
- Standardise Testcontainers.
- Remove duplicated fixtures.
- Improve test isolation.

Recommendations should preserve repository behaviour.

---

# Risks

Examples

- Missing integration tests
- Shared test database
- Slow test execution
- Flaky tests
- Inconsistent fixtures

Classify

Low

Medium

High

---

# Questions Raised

Examples

- Can Testcontainers replace shared databases?
- Are all repositories covered?
- Is manual validation still required?
- Can feature tests be automated?

---

# Assumptions

Document assumptions made during discovery.

Examples

- Tests not executed.
- Coverage inferred.
- Local environment unavailable.

If uncertain

record

```
Requires Human Confirmation
```

---

# References

Related Repository Context

- build.md
- database.md
- projects.md

Related Engineering Standards

- Oracle → PostgreSQL
- Testcontainers

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

✓ Testing strategy documented

✓ Test projects documented

✓ Test frameworks documented

✓ Test infrastructure documented

✓ Database testing documented

✓ Test harness documented

✓ Validation workflow documented

✓ Facts recorded

✓ Observations recorded

✓ Recommendations recorded

✓ Risks documented

✓ Questions Raised documented

✓ Assumptions documented

✓ Confidence assessed
