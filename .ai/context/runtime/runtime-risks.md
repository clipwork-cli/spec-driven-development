# Runtime Risk Assessment

---

# Purpose

This document identifies engineering risks that affect application behaviour during runtime.

Its purpose is to help architects, engineers and AI agents understand operational risks before implementation, modernization or migration begins.

This document should answer

> "What runtime behaviours introduce engineering risk?"

Repository implementation risks are documented separately in Repository Context.

---

# Scope

This document covers

- Runtime dependencies
- Operational risks
- Availability risks
- Reliability risks
- Performance risks
- Integration risks
- Data consistency risks
- Recovery risks

Business risks are out of scope.

---

# Runtime Risk Summary

Summarise overall runtime health.

Document

- Overall Runtime Risk
- Availability
- Reliability
- Performance
- Operational Readiness

Example

Overall Runtime Risk

Medium

Primary Drivers

- Oracle dependency
- Long-running reporting
- Limited observability

---

# Runtime Risk Register

Document every runtime risk.

---

## Risk

### Identifier

```
RUNTIME-RISK-001
```

---

### Title

Example

```
Oracle Connection Saturation
```

---

### Category

Examples

- Availability
- Reliability
- Performance
- Integration
- Database
- Messaging
- Operations
- Observability

---

### Description

Describe the runtime behaviour introducing the risk.

---

### Business Capabilities

Reference

```
capabilities.md
```

Identify affected capabilities.

---

### Runtime Flows

Reference

```
runtime-flow.md
```

---

### Integrations

Reference

```
integrations.md
```

---

### Operations

Reference

```
operations.md
```

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

### Runtime Impact

Examples

- User request failures
- Slow responses
- Background processing delays
- Synchronization failures
- Reporting unavailable

---

### Detection

Describe how the risk is detected.

Examples

- Logs
- Metrics
- Alerts
- Dashboards
- Manual Monitoring

If unavailable

```
Unknown
```

---

### Recovery

Describe current recovery behaviour.

Examples

- Retry
- Restart
- Failover
- Manual Recovery
- Dead Letter Queue

---

### Mitigation Opportunities

Examples

- Reduce Oracle dependency
- Add retries
- Improve monitoring
- Parallelize processing
- Introduce caching

These are engineering recommendations only.

---

# Availability Risks

Examples

- Single database dependency
- Single external API
- Missing failover
- Shared infrastructure

---

# Performance Risks

Examples

- Long-running SQL
- Large reporting queries
- Blocking operations
- Sequential processing

---

# Reliability Risks

Examples

- Missing retries
- Duplicate processing
- Shared mutable state
- Inconsistent transactions

---

# Integration Risks

Examples

- External API dependency
- SAP availability
- Oracle dependency
- Kafka outages

---

# Operational Risks

Examples

- Manual recovery
- Limited monitoring
- Missing alerts
- Background job failures

---

# Migration Risks

Assess runtime risks that may impact modernization.

Examples

- Oracle and PostgreSQL behavioural differences
- Transaction semantics
- Query performance changes
- Connection pooling differences
- Data consistency validation
- Stored Procedure replacement

These risks are specific to engineering initiatives.

---

# Runtime Hotspots

Identify areas where multiple runtime risks overlap.

Examples

Reporting

- Oracle
- Long SQL
- Shared Views
- Large Transactions

Synchronization

- SAP
- Kafka
- Oracle
- Retry Logic

These hotspots should receive additional architectural attention.

---

# Facts

Record verified facts.

Examples

- Reporting executes five Oracle queries.
- Synchronization depends on SAP availability.
- Queue processing lacks retries.

Facts should be directly observable.

---

# Observations

Examples

- Runtime heavily dependent on Oracle.
- Most failures originate from integrations.
- Background processing has limited visibility.

Observations should be evidence-based.

---

# Recommendations

Examples

- Migrate low-risk capabilities first.
- Instrument critical runtime flows.
- Add retry policies.
- Improve health monitoring before migration.

Recommendations should preserve business behaviour.

---

# Questions Raised

Examples

- Can reporting be isolated?
- Which runtime flows require performance testing?
- Which integrations require failover validation?
- Is Oracle the primary runtime bottleneck?

---

# Assumptions

Document assumptions made during discovery.

Examples

- Runtime behaviour inferred from source code.
- Production metrics unavailable.
- Load characteristics unknown.

If uncertain

```
Requires Human Confirmation
```

---

# References

Repository Context

- database.md
- testing.md
- modernization.md
- risks.md

Runtime Context

- capabilities.md
- runtime-flow.md
- integrations.md
- operations.md
- data-flow.md
- observability.md

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

✓ Runtime risks identified

✓ Business capabilities mapped

✓ Runtime flows mapped

✓ Integration risks documented

✓ Operational risks documented

✓ Migration risks documented

✓ Runtime hotspots identified

✓ Facts recorded

✓ Observations recorded

✓ Recommendations recorded

✓ Questions Raised documented

✓ Assumptions documented

✓ Confidence assessed
