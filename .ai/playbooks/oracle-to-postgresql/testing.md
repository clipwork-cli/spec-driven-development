# Oracle → PostgreSQL Testing Standard

---

# Purpose

This Engineering Standard defines how Oracle → PostgreSQL migrations should be validated.

The objective is to provide engineering evidence that business behaviour has been preserved after migration.

Testing should validate behaviour rather than implementation.

---

# Engineering Principles

Oracle → PostgreSQL migrations should

- Preserve business behaviour
- Preserve API contracts
- Preserve integration behaviour
- Preserve transactional behaviour
- Preserve operational behaviour

Implementation differences are acceptable.

Behavioural differences are not.

---

# Testing Pyramid

Every Specification should use the following validation strategy.

```
Manual Validation

↑

Integration Tests

↑

Repository Tests

↑

Unit Tests
```

Priority should be given to integration testing.

---

# Unit Testing

Unit tests validate

- Business rules
- Domain logic
- Mapping
- Validation
- Utility methods

Unit tests should not verify SQL translation.

---

# Repository Testing

Repository tests validate

- Repository behaviour
- Query execution
- CRUD operations
- Transaction behaviour

Repository tests should execute against PostgreSQL.

Mocking database behaviour is discouraged.

---

# Integration Testing

Integration tests provide the primary migration validation.

Integration tests should verify

- Business Capability behaviour
- API contracts
- Database interactions
- Runtime behaviour
- Integration behaviour

Integration tests should execute against PostgreSQL.

---

# Testcontainers

Testcontainers is the preferred execution environment.

Where available

use Testcontainers.

Example

```
PostgreSQLContainer

↓

Repository Tests

↓

Integration Tests
```

Testcontainers should provision PostgreSQL automatically.

Avoid shared developer databases.

---

# Local PostgreSQL

If Testcontainers are unavailable

use a local PostgreSQL Docker container.

Example

```
docker run

↓

PostgreSQL

↓

Repository Tests

↓

Integration Tests
```

Local database configuration should be documented.

---

# Existing Repositories

When existing integration tests exist

reuse them.

Do not rewrite tests unnecessarily.

Existing validation provides valuable behavioural evidence.

---

# New Integration Tests

When integration coverage is insufficient

add integration tests before migration begins.

Priority should be given to

- Business Capabilities
- Runtime Flows
- Repository behaviour

Testing should protect behaviour before code changes.

---

# Behaviour Preservation

Every migrated Specification should verify

## Business Behaviour

Examples

- Search results
- Commands
- Validation
- Error handling

---

## API Behaviour

Verify

- Request contract
- Response contract
- HTTP status codes
- Error responses

---

## Database Behaviour

Verify

- CRUD operations
- Transactions
- Constraints
- Views
- Stored Procedures (if translated)
- Functions

---

## Integration Behaviour

Verify

- External APIs
- Messaging
- Events
- Background processing

---

## Operational Behaviour

Verify

- Scheduled jobs
- Workers
- Synchronization
- Retry behaviour

---

# SQL Validation

Validate translated SQL.

Examples

- Result set equivalence
- NULL handling
- Pagination
- Sorting
- Aggregation
- Date/time handling
- String comparison

Translated SQL should produce equivalent business results.

---

# Stored Procedures

When Stored Procedures are translated

validate

- Inputs
- Outputs
- Transactions
- Error handling

Prefer behavioural verification over statement comparison.

---

# Views

Translated views should be validated using

- Representative datasets
- Existing integration tests
- Business scenarios

View definitions do not need to match Oracle implementation.

Business results must match.

---

# Transactions

Validate

- Commit
- Rollback
- Isolation assumptions
- Concurrency behaviour

Document any PostgreSQL-specific differences.

---

# Performance Validation

Performance testing is not mandatory unless required by the Specification.

When performed

compare

- Execution time
- Query plans
- Resource utilisation

Behaviour takes precedence over performance.

---

# Test Data

Use representative data.

Avoid

- Artificial happy-path only datasets
- Minimal datasets
- Hardcoded production data

Representative business scenarios should be prioritised.

---

# Validation Evidence

Every Specification should provide evidence.

Examples

- Unit test results
- Integration test results
- Testcontainers execution
- Build logs
- Manual validation
- SQL verification

Evidence should be referenced in

```
validation.md
```

---

# Failure Handling

When validation fails

Determine whether the issue is

- Translation error
- Schema issue
- Business logic issue
- PostgreSQL behaviour
- Test issue

Do not modify behaviour to satisfy tests without understanding the root cause.

---

# Human Validation

AI cannot determine whether business behaviour is correct.

Human validation is required for

- Business workflows
- User acceptance
- Operational verification
- Production readiness

---

# Success Criteria

Oracle → PostgreSQL testing is complete when

✓ Repository tests pass

✓ Integration tests pass

✓ Business behaviour preserved

✓ API contracts preserved

✓ Database behaviour validated

✓ Runtime behaviour validated

✓ Validation evidence documented

✓ Human verification completed where required
