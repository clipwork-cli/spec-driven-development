# Engineering Review

---

# Review Metadata

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

## Reviewer

Reviewer

---

## Review Status

Examples

- Draft
- In Review
- Approved
- Changes Required
- Rejected

---

## Review Date

YYYY-MM-DD

---

# Purpose

The Engineering Review validates that the implementation satisfies the approved Engineering Specification.

The Review validates

- Scope
- Behaviour
- Engineering Standards
- Validation Evidence

The Review does not introduce new scope.

The Review does not redesign the solution.

---

# Review Inputs

Review the following artifacts.

Specification

```
specification.md
```

Implementation Plan

```
plan.md
```

Engineering Tasks

```
tasks.md
```

Validation Evidence

```
validation.md
```

Repository Context

Runtime Context

Applicable Engineering Standards

Pull Request

---

# Scope Validation

Confirm

✓ Approved Specification implemented

✓ No additional scope introduced

✓ No Specification requirements omitted

Document any deviations.

---

# Behaviour Preservation

Validate

## Business Behaviour

Preserved

Yes / No

Comments

---

## API Behaviour

Preserved

Yes / No

Comments

---

## Database Behaviour

Preserved

Yes / No

Comments

---

## Integration Behaviour

Preserved

Yes / No

Comments

---

## Operational Behaviour

Preserved

Yes / No

Comments

---

# Engineering Standards Validation

Validate compliance with

- Oracle → PostgreSQL
- Modernization
- Test Harness
- Coding Standards

Document any violations.

---

# Repository Impact Review

Validate

- Architecture preserved
- Repository boundaries respected
- Dependencies acceptable
- No architectural drift

Reference Repository Context where appropriate.

---

# Runtime Impact Review

Validate

- Business Capability preserved
- Runtime Flow preserved
- Data Flow preserved
- Operations preserved
- Integrations preserved

Reference Runtime Context.

---

# Code Quality Assessment

Assess

- Readability
- Maintainability
- Simplicity
- Consistency
- Error Handling
- Logging
- Configuration

Focus on engineering quality.

Avoid subjective preferences.

---

# Validation Review

Validate engineering evidence.

Examples

✓ Build succeeds

✓ Unit Tests pass

✓ Integration Tests pass

✓ Testcontainers pass

✓ Manual Validation completed

✓ Behaviour preserved

Review evidence.

Do not rerun implementation.

---

# Findings

Document findings.

For each finding include

Identifier

Severity

Examples

- Informational
- Minor
- Major
- Critical

Description

Recommendation

Reference

Specification

Plan

Task

Engineering Standard

---

# Outstanding Issues

Document unresolved issues.

If none

```
None
```

---

# Recommendation

Select one.

- Approve
- Approve with Recommendations
- Changes Required
- Return to Planner
- Return to Architect

Explain the rationale.

---

# Lessons Learned

Document reusable engineering knowledge.

Examples

- Better repository pattern discovered
- Improved SQL translation approach
- Better Testcontainers setup
- Common Oracle migration issue

Lessons Learned may be promoted into Engineering Standards.

---

# Review Summary

Summarise

- Implementation quality
- Behaviour preservation
- Engineering quality
- Outstanding risks

Keep this concise.

---

# Success Criteria

The Review is complete when

✓ Specification validated

✓ Scope validated

✓ Behaviour preserved

✓ Engineering Standards satisfied

✓ Validation evidence reviewed

✓ Findings documented

✓ Recommendation issued

✓ Ready for Human Approval
