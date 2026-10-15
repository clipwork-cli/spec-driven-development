# Runtime Data Flow

---

# Purpose

This document describes how business data moves through the application at runtime.

Its purpose is to help engineers understand how information is created, transformed, persisted and exchanged across Business Capabilities.

This document should answer

> "How does business data flow through the system?"

This document complements Runtime Flow.

Runtime Flow describes execution.

Data Flow describes information movement.

---

# Scope

This document covers

- Request data
- Domain data
- Persistence
- External data exchange
- Messaging
- Data transformations
- Data ownership
- Data boundaries

This document does not describe physical database schema.

---

# Data Flow Summary

Document

- Major business entities
- Data producers
- Data consumers
- External systems
- Messaging systems
- Persistence layers

Summarise the overall information flow.

---

# Business Entity Inventory

Document every major business entity.

---

## Entity

### Identifier

```
DATA-001
```

---

### Name

```
Asset
```

---

### Business Capability

Reference

```
capabilities.md
```

---

### Description

Describe the business meaning of the entity.

---

### Source

Examples

- User Input
- Oracle
- PostgreSQL
- SAP
- Kafka
- File Import

---

### Consumers

Examples

- Reporting
- Search
- Synchronization

---

### Storage

Examples

- Oracle Table
- PostgreSQL Table
- Cache
- File

Reference

```
repository/database.md
```

---

### Lifetime

Examples

- Request Only
- Persisted
- Cached
- Event

---

### Ownership

Document which Business Capability owns the entity.

If shared

identify all owners.

---

# Data Flow Inventory

Document every significant data flow.

---

## Data Flow

### Identifier

```
FLOW-DATA-001
```

---

### Name

```
Asset Search Request
```

---

### Trigger

Examples

- HTTP Request
- Kafka Event
- Scheduled Job
- Manual Execution

---

### Input

Describe incoming data.

---

### Processing

Describe transformations.

Examples

Validation

↓

Business Rules

↓

Mapping

↓

Persistence

---

### Output

Describe produced data.

---

### Destination

Examples

- Oracle
- PostgreSQL
- SAP
- Kafka
- Response

---

### Business Capability

Reference

```
capabilities.md
```

---

### Runtime Flow

Reference

```
runtime-flow.md
```

---

### Data Transformations

Document

- Mapping
- Enrichment
- Aggregation
- Filtering

Avoid implementation details.

---

### Validation

Describe validation rules.

Examples

- Required fields
- Business validation
- Referential checks

---

### Error Handling

Examples

- Reject
- Retry
- Dead Letter Queue
- Manual Review

---

# Shared Data

Identify entities shared across multiple capabilities.

Examples

- Asset
- User
- Location
- Work Order

Shared entities often indicate coupling.

---

# Data Ownership

Document ownership boundaries.

Example

Asset

↓

Asset Search

Reporting (Read Only)

Synchronization (Read/Write)

Ownership should align with Business Capabilities.

---

# Persistence Strategy

Summarise

- CRUD
- Event-driven
- Read models
- Caching

Reference Repository Context where appropriate.

---

# Facts

Examples

- Asset entity stored in Oracle.
- Reporting aggregates five tables.
- Synchronization enriches Asset data from SAP.

Facts should be directly observable.

---

# Observations

Examples

- Reporting duplicates data transformations.
- Asset entity shared by many capabilities.
- Data ownership unclear.

---

# Recommendations

Examples

- Clarify ownership.
- Reduce duplicated transformations.
- Simplify persistence path.

Recommendations should preserve business behaviour.

---

# Risks

Examples

- Shared mutable data
- Duplicate transformations
- Multiple system of record
- Data consistency
- Tight database coupling

Classify

- Low
- Medium
- High

---

# Questions Raised

Examples

- Which capability owns Asset?
- Can transformations be consolidated?
- Is Oracle the system of record?
- Can reporting use PostgreSQL independently?

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

- database.md

Runtime Context

- capabilities.md
- runtime-flow.md
- integrations.md
- operations.md

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

✓ Business entities identified

✓ Data ownership documented

✓ Data flows documented

✓ Data transformations documented

✓ Persistence strategy documented

✓ Shared entities identified

✓ Facts recorded

✓ Observations recorded

✓ Recommendations recorded

✓ Risks documented

✓ Questions Raised documented

✓ Assumptions documented

✓ Confidence assessed
