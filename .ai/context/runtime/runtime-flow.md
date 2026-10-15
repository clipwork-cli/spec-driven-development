# Runtime Flow

---

# Purpose

This document describes how requests, commands and events execute through the application at runtime.

Its purpose is to help engineers understand application behaviour independently of repository structure.

This document should answer

> "How does this capability execute from start to finish?"

Runtime Flow complements Repository Context.

Repository Context describes implementation.

Runtime Flow describes behaviour.

---

# Scope

This document covers

- Request lifecycle
- Command execution
- Query execution
- Background processing
- Event processing
- Database interaction
- External integrations
- Error propagation

Implementation details belong in Repository Context.

---

# Runtime Summary

Document

- Runtime architecture
- Primary execution patterns
- Entry point types
- Integration styles
- Database interaction model

Examples

- Request / Response
- Event Driven
- Batch Processing
- Scheduled Jobs

---

# Runtime Patterns

Identify the primary runtime patterns.

Examples

- HTTP Request
- CQRS
- Publish / Subscribe
- Background Worker
- Queue Consumer
- Batch Processing

For each pattern describe its purpose.

---

# Runtime Flow Inventory

Document every major runtime flow.

---

## Runtime Flow

### Name

```
Asset Search
```

---

### Business Capability

Reference

```
capabilities.md
```

---

### Trigger

Examples

- HTTP Request
- Kafka Event
- Timer
- Scheduled Job
- Azure Service Bus
- Manual Execution

---

### Execution Flow

Document the major runtime path.

Example

```
HTTP Request

↓

Authentication

↓

Controller

↓

Application Service

↓

Repository

↓

Oracle

↓

Response
```

Focus on logical execution.

Not implementation classes.

---

### Runtime Components

Examples

- Controller
- Handler
- Service
- Repository
- Queue Consumer
- Worker

Document responsibilities.

---

### Database Interaction

Describe

- Reads
- Writes
- Transactions
- Stored Procedures
- Views

Reference

```
repository/database.md
```

---

### External Integrations

Document runtime interactions.

Examples

- SAP
- Oracle
- Kafka
- REST APIs

---

### Failure Points

Identify possible runtime failures.

Examples

- Authentication
- Database timeout
- External API
- Queue failure
- Validation

---

### Recovery Strategy

Examples

- Retry
- Dead Letter Queue
- Manual Retry
- Fail Fast

If unknown

```
Unknown
```

---

### Observability

Document runtime visibility.

Examples

- Logs
- Metrics
- Tracing
- Health Checks

---

# Shared Runtime Flows

Identify shared runtime behaviour.

Examples

Authentication

↓

Authorization

↓

Validation

↓

Logging

↓

Database

Avoid duplicating shared flows across capabilities.

---

# Runtime Dependencies

Document dependencies between runtime flows.

Example

```
Authentication

↓

Asset Search

↓

Reporting

↓

Notifications
```

Dependencies should reflect runtime behaviour.

---

# Runtime Bottlenecks

Identify execution bottlenecks.

Examples

- Long-running SQL
- Shared services
- External API latency
- Sequential processing
- Synchronous integrations

---

# Facts

Record verified runtime facts.

Examples

- Asset Search performs three database queries.
- Reporting calls SAP synchronously.
- Synchronization publishes Kafka events.

Facts should be supported by evidence.

---

# Observations

Examples

- Runtime flow is highly synchronous.
- Reporting tightly coupled to Oracle.
- Validation duplicated across controllers.

---

# Recommendations

Recommend runtime improvements.

Examples

- Introduce asynchronous processing.
- Reduce database round trips.
- Improve retry handling.

Recommendations should preserve business behaviour.

---

# Risks

Examples

- Long-running transactions
- External API dependency
- Shared runtime bottlenecks
- Missing retries
- Oracle latency

Classify

Low

Medium

High

---

# Questions Raised

Examples

- Can reporting become asynchronous?
- Are retries implemented consistently?
- Is Oracle the primary bottleneck?
- Can runtime flow be simplified?

---

# Assumptions

Examples

- Runtime flow inferred from source code.
- Production configuration unavailable.
- Runtime metrics unavailable.

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
- operations.md
- integrations.md

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

✓ Runtime patterns identified

✓ Runtime flows documented

✓ Entry points identified

✓ Database interactions documented

✓ External integrations documented

✓ Runtime dependencies documented

✓ Failure points identified

✓ Recovery strategies documented

✓ Observability documented

✓ Runtime bottlenecks identified

✓ Facts recorded

✓ Observations recorded

✓ Recommendations recorded

✓ Risks documented

✓ Questions Raised documented

✓ Assumptions documented

✓ Confidence assessed
