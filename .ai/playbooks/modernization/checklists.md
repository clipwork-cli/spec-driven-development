# Modernization Checklist

---

# Purpose

This checklist defines the minimum engineering activities required for every modernization initiative.

Its purpose is to ensure modernization work is consistent, repeatable and independently verifiable.

This checklist complements the Modernization Engineering Standard and should be used throughout the engineering lifecycle.

---

# Usage

The checklist should be reviewed during

- Specification
- Planning
- Implementation
- Validation
- Engineering Review

Every applicable item should be completed before implementation is considered finished.

---

# Discovery

Before creating a Specification

✓ Repository Context completed

✓ Runtime Context completed

✓ Repository risks understood

✓ Runtime risks understood

✓ Business Capability identified

✓ Engineering Standards identified

✓ Modernization candidate confirmed

---

# Specification

Before planning begins

✓ Business Capability defined

✓ Behaviour Preservation documented

✓ Scope defined

✓ Out-of-scope documented

✓ Engineering Standards referenced

✓ Acceptance Criteria completed

✓ Repository Context referenced

✓ Runtime Context referenced

---

# Planning

Before implementation begins

✓ Implementation strategy approved

✓ Validation strategy documented

✓ Rollback strategy documented

✓ Risk mitigation documented

✓ Test Harness identified

✓ Dependencies documented

✓ Engineering decisions recorded

✓ Tasks generated

---

# Implementation

During implementation

✓ Behaviour preserved

✓ Scope unchanged

✓ Existing architecture respected

✓ Repository boundaries maintained

✓ Engineering Standards followed

✓ Documentation updated where required

✓ No unnecessary refactoring introduced

---

# Testing

Before Engineering Review

✓ Build succeeds

✓ Static analysis passes

✓ Existing tests pass

✓ New tests pass

✓ Integration tests executed

✓ Manual validation completed (if required)

✓ Behaviour preserved

---

# Validation

Before Engineering Review

✓ Validation evidence documented

✓ Test reports attached

✓ Build logs available

✓ Performance evidence recorded (if applicable)

✓ Database validation completed (if applicable)

✓ Validation outcome recorded

---

# Engineering Review

Before Human Approval

✓ Specification satisfied

✓ Scope preserved

✓ Behaviour preserved

✓ Engineering Standards satisfied

✓ Validation evidence reviewed

✓ Findings resolved

✓ Outstanding issues documented

---

# Documentation

Before merging

✓ Repository Context updated (if required)

✓ Runtime Context updated (if required)

✓ Specification completed

✓ Review completed

✓ Validation completed

✓ Lessons Learned captured

---

# Merge Readiness

A modernization Specification is ready to merge when

✓ Engineering Review approved

✓ Human approval obtained

✓ Validation completed

✓ Behaviour preserved

✓ Documentation updated

✓ Outstanding risks accepted or resolved

---

# Anti-Patterns

Do not

✗ Skip Discovery

✗ Skip Repository Context

✗ Skip Runtime Context

✗ Skip Behaviour Preservation

✗ Skip validation

✗ Expand Specification scope

✗ Combine unrelated modernization initiatives

✗ Refactor while modernizing without approval

✗ Remove legacy code before validating the replacement

---

# Success Criteria

A successful modernization effort

✓ Preserves business behaviour

✓ Reduces engineering risk

✓ Improves maintainability

✓ Produces reusable engineering knowledge

✓ Leaves the repository in a better state than before
