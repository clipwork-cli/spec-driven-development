# Runtime Integrations

---

# Purpose

This document describes how the application interacts with external systems at runtime.

Its purpose is to help engineers understand integration boundaries, communication patterns and external dependencies.

This document should answer

> "What external systems does the application rely on?"

It complements Repository Context by focusing on runtime interactions rather than implementation.

---

# Scope

This document covers

- External systems
- Communication patterns
- Integration ownership
- Authentication
- Error handling
- Retry behaviour
- Dependency criticality

Implementation details belong in Repository Context.

---

# Integration Summary

Document

- Total external systems
- Internal services
- Databases
- Message brokers
- File integrations
- Third-party services

Summarise the overall integration landscape.

---

# Integration Inventory

Document every runtime integration.

---

## Integration

### Name

```
Oracle Database
```

---

### Type

Examples

- Database
- REST API
- SOAP Service
- Kafka
- Azure Service Bus
- File Share
- FTP
- SMTP

---

### Purpose

Describe why the application communicates with this system.

---

### Business Capabilities

Reference

```
capabilities.md
```

List every capability that depends on this integration.

---

### Runtime Flows

Reference

```
runtime-flow.md
```

List the runtime flows that use this integration.

---

### Communication Pattern

Examples

- Synchronous
- Asynchronous
- Request / Response
- Publish / Subscribe
- Scheduled Synchronization
- Batch Processing

---

### Authentication

Examples

- Active Directory
- OAuth2
- API Key
- Certificate
- Anonymous

---

### Failure Behaviour

Document expected behaviour when the integration is unavailable.

Examples

- Retry
- Fail Fast
- Dead Letter Queue
- Circuit Breaker
- Manual Recovery

If unknown

```
Unknown
```

---

### Criticality

Classify

- Low
- Medium
- High
- Critical

Criticality represents runtime dependency.

---

### Ownership

If known

Document

- Internal Team
- External Vendor

Otherwise

```
Unknown
```

---

# Integration Relationships

Document how integrations interact.

Example

```
Application

↓

Oracle

↓

SAP

↓

Kafka
```

Focus on runtime relationships.

---

# Shared Integrations

Identify integrations shared across multiple capabilities.

Examples

- Authentication
- Oracle
- Kafka
- SAP

Shared integrations often represent architectural hotspots.

---

# Integration Resilience

Assess

- Retry mechanisms
- Timeout handling
- Circuit breakers
- Fallback behaviour
- Idempotency

Document observed patterns.

---

# Integration Hotspots

Identify integrations that

- support many capabilities
- introduce significant coupling
- are difficult to replace
- are operationally critical

Examples

Oracle Database

Supports

12 Business Capabilities

Criticality

Critical

---

# Facts

Record verified facts.

Examples

- Reporting calls SAP synchronously.
- Asset Search queries Oracle directly.
- Synchronization publishes Kafka events.

Facts should be directly observable.

---

# Observations

Examples

- Oracle is the primary integration dependency.
- Most integrations are synchronous.
- Retry behaviour inconsistent across capabilities.

Observations should be supported by evidence.

---

# Recommendations

Recommend engineering improvements.

Examples

- Standardise retry behaviour.
- Introduce circuit breakers.
- Reduce Oracle coupling.
- Isolate external API clients.

Recommendations should preserve business behaviour.

---

# Risks

Examples

- Critical external dependency
- Long-running integrations
- Missing retries
- Tight coupling
- Shared integration bottlenecks

Classify

- Low
- Medium
- High

---

# Questions Raised

Examples

- Can Oracle dependency be reduced?
- Which integrations can be mocked?
- Can synchronous calls become asynchronous?
- Are all integrations still active?

---

# Assumptions

Document assumptions made during discovery.

Examples

- Integration inferred from source code.
- Authentication not verified.
- Retry behaviour inferred.

If uncertain

```
Requires Human Confirmation
```

---

# References

Repository Context

- entry-points.md
- dependencies.md
- database.md

Runtime Context

- capabilities.md
- runtime-flow.md

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

✓ External systems identified

✓ Communication patterns documented

✓ Business capabilities mapped

✓ Runtime flows mapped

✓ Authentication documented

✓ Failure behaviour documented

✓ Shared integrations identified

✓ Integration hotspots documented

✓ Facts recorded

✓ Observations recorded

✓ Recommendations recorded

✓ Risks documented

✓ Questions Raised documented

✓ Assumptions documented

✓ Confidence assessed
