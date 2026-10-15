# Runtime Operations

---

# Purpose

This document describes long-running and background operations performed by the application.

Its purpose is to provide engineers and AI agents with a complete understanding of operational behaviour outside normal request processing.

This document should answer

> "What work does the application perform automatically?"

Operations complement Runtime Flows by describing autonomous or recurring execution.

---

# Scope

This document covers

- Scheduled jobs
- Background workers
- Queue consumers
- Batch processing
- Synchronization
- Import / Export
- Maintenance tasks
- Housekeeping
- Event processing

Interactive request processing belongs in Runtime Flow.

---

# Operations Summary

Document

- Total Operations
- Scheduled Jobs
- Background Workers
- Queue Consumers
- Batch Jobs
- Maintenance Tasks

Summarise operational complexity.

---

# Operation Inventory

Document every runtime operation.

---

## Operation

### Identifier

```
OP-001
```

---

### Name

```
Nightly Asset Synchronization
```

---

### Type

Examples

- Scheduled Job
- Background Worker
- Queue Consumer
- Batch Process
- Timer
- Hosted Service
- Windows Service
- Azure Function

---

### Business Capability

Reference

```
capabilities.md
```

An operation belongs to one primary Business Capability.

If shared

document all affected capabilities.

---

### Trigger

Examples

- Cron Schedule
- Timer
- Kafka Event
- Azure Service Bus
- File Arrival
- Manual Execution
- Startup

---

### Schedule

Examples

```
Daily 02:00

Every 15 Minutes

Hourly

On Demand
```

If not applicable

```
N/A
```

---

### Purpose

Describe the business outcome.

Focus on business value rather than implementation.

---

### Runtime Flow

Reference

```
runtime-flow.md
```

---

### Runtime Components

Examples

- Hosted Service
- Worker
- Repository
- Service
- Handler

Describe responsibilities.

---

### Database Usage

Document

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

Reference

```
integrations.md
```

---

### Inputs

Examples

- Queue Message
- File
- Timer
- API
- Database

---

### Outputs

Examples

- Database
- Kafka
- REST API
- Report
- File

---

### Failure Behaviour

Examples

- Retry
- Fail Fast
- Dead Letter Queue
- Resume Next Run
- Manual Recovery

If unknown

```
Unknown
```

---

### Idempotency

Document

- Yes
- No
- Unknown

Describe how duplicate execution is handled.

---

### Monitoring

Examples

- Logs
- Metrics
- Alerts
- Dashboard
- Health Checks

---

# Operational Relationships

Document dependencies between operations.

Example

```
OP-001

↓

OP-003

↓

OP-008
```

Only document operational dependencies.

---

# Operational Hotspots

Identify operations that

- take significant time
- perform many database operations
- integrate with multiple systems
- support multiple capabilities

Examples

Nightly Synchronization

Supports

7 Business Capabilities

Criticality

High

---

# Facts

Examples

- Repository contains six scheduled jobs.
- Three Kafka consumers.
- One nightly synchronization process.

Facts should be directly observable.

---

# Observations

Examples

- Operations heavily dependent on Oracle.
- Synchronization is sequential.
- Retry behaviour inconsistent.

Observations should be evidence-based.

---

# Recommendations

Examples

- Improve operation isolation.
- Standardize retry strategy.
- Reduce Oracle dependency.
- Improve monitoring.

Recommendations should preserve business behaviour.

---

# Risks

Examples

- Long-running jobs
- Missing retries
- Duplicate execution
- Shared state
- Manual recovery

Classify

- Low
- Medium
- High

---

# Questions Raised

Examples

- Can synchronization run in parallel?
- Are all scheduled jobs still required?
- Which jobs can migrate independently?
- Which operations are business critical?

---

# Assumptions

Document assumptions.

If uncertain

```
Requires Human Confirmation
```

---

# References

Repository Context

- entry-points.md
- database.md
- testing.md

Runtime Context

- capabilities.md
- runtime-flow.md
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

✓ Scheduled jobs documented

✓ Background workers documented

✓ Queue consumers documented

✓ Batch processes documented

✓ Business capabilities mapped

✓ Runtime flows referenced

✓ Database interactions documented

✓ External integrations documented

✓ Monitoring documented

✓ Facts recorded

✓ Observations recorded

✓ Recommendations recorded

✓ Risks documented

✓ Questions Raised documented

✓ Assumptions documented

✓ Confidence assessed
