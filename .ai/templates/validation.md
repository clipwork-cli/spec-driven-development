# Engineering Validation

---

# Validation Metadata

## Specification

```
SPEC-001
```

---

## Title

Example

```
Oracle → PostgreSQL Migration — Asset Search
```

---

## Owner

Developer

Validated by Reviewer

---

## Status

Examples

- Draft
- In Progress
- Ready for Review
- Approved

---

## Validation Date

YYYY-MM-DD

---

# Purpose

Engineering Validation provides evidence that the implementation satisfies the approved Engineering Specification.

Validation demonstrates

- Behaviour Preservation
- Engineering Quality
- Specification Compliance

Validation is evidence.

Not opinion.

---

# Validation Inputs

Reference

```
specification.md

plan.md

tasks.md

review.md
```

Reference applicable Engineering Standards.

---

# Behaviour Preservation

## Business Behaviour

Evidence

Examples

- Screenshots
- API responses
- Functional validation
- Business verification

Outcome

Pass / Fail

Comments

---

## API Behaviour

Evidence

Examples

- Contract tests
- API comparison
- Response validation

Outcome

Pass / Fail

---

## Database Behaviour

Evidence

Examples

- SQL comparison
- Data verification
- Query results
- Stored Procedure comparison

Outcome

Pass / Fail

---

## Integration Behaviour

Evidence

Examples

- Integration tests
- External API validation
- Kafka validation
- Queue validation

Outcome

Pass / Fail

---

## Operational Behaviour

Evidence

Examples

- Scheduled job execution
- Worker execution
- Monitoring
- Logs

Outcome

Pass / Fail

---

# Build Validation

Document

✓ Restore succeeded

✓ Build succeeded

✓ Static analysis passed

✓ Formatting passed

Attach evidence where appropriate.

---

# Test Validation

Document

## Unit Tests

Executed

Pass / Fail

Evidence

---

## Integration Tests

Executed

Pass / Fail

Evidence

---

## Feature Validation

Executed

Pass / Fail

Evidence

---

## Manual Validation

Executed

Pass / Fail

Evidence

---

# Test Harness Validation

Document

- Testcontainers
- Docker
- Local PostgreSQL
- Shared Fixtures

Record execution evidence.

---

# Database Validation

Applicable to database changes.

Document

- SQL translation verified
- PostgreSQL execution verified
- Stored Procedures validated
- Views validated
- Transactions validated

Reference the PostgreSQL schema version used for validation.

---

# Performance Validation

If applicable

Document

- Baseline
- New Result
- Observations

Performance regressions should be documented.

---

# Engineering Standards Validation

Confirm compliance with

- Oracle → PostgreSQL
- Modernization
- Test Harness
- Coding Standards

Record any deviations.

---

# Known Limitations

Document limitations.

Examples

- Performance not benchmarked
- Production validation pending
- Manual validation incomplete

If none

```
None
```

---

# Validation Summary

Summarise

- Behaviour preserved
- Engineering Standards satisfied
- Outstanding limitations
- Confidence level

---

# Validation Outcome

Select one.

- Passed
- Passed with Limitations
- Failed
- Requires Further Validation

Explain the decision.

---

# Evidence References

Reference supporting material.

Examples

- Build logs
- Test reports
- Screenshots
- SQL comparison
- Pull Request
- Pipeline execution
- Performance report

---

# Success Criteria

Validation is complete when

✓ Behaviour preserved

✓ Build validated

✓ Tests validated

✓ Database validated (if applicable)

✓ Engineering Standards satisfied

✓ Evidence documented

✓ Reviewer can independently verify the implementation
