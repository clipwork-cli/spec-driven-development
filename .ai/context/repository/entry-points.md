# Entry Points

---

# Purpose

This document identifies every executable entry point within the repository.

Its purpose is to help engineers and AI agents understand how execution enters the application and where business capabilities originate.

This document should answer

> "Where does execution begin?"

It should not describe runtime behaviour in detail.

Runtime execution is documented separately in Runtime Context.

---

# Scope

This document covers

- HTTP entry points
- Background workers
- Queue consumers
- Scheduled jobs
- Hosted services
- CLI applications
- Azure Functions
- Windows Services
- SignalR hubs
- Event handlers

This document does not describe business logic.

---

# Entry Point Summary

Document

- Total Entry Points
- APIs
- Workers
- Background Services
- Scheduled Jobs
- Queue Consumers
- Function Apps
- Desktop Applications

---

# Entry Point Inventory

Document every entry point.

---

## Entry Point

### Name

```
AssetController
```

### Type

Examples

- API Controller
- Hosted Service
- Queue Consumer
- Background Worker
- Azure Function
- Windows Service
- Console Application

---

### Location

Project

Namespace

Class

---

### Trigger

Examples

- HTTP Request
- Timer
- Kafka
- Azure Service Bus
- RabbitMQ
- Scheduled Job
- Manual Execution

---

### Business Capability

Document the primary Business Capability.

If unknown

```
Unknown
```

---

### Dependencies

Examples

- Services
- Repositories
- External APIs
- Messaging
- Storage

---

### Database Usage

Examples

- Oracle
- PostgreSQL
- None

---

### Authentication

Examples

- Anonymous
- JWT
- Active Directory
- OAuth

---

### Consumers

Identify upstream callers if known.

---

# API Endpoints

Summarise

- Controllers
- Route prefixes
- Versioning
- Authentication

---

# Background Processing

Document

- Hosted Services
- Windows Services
- Timers
- Cron Jobs
- Batch Processing

---

# Event Processing

Document

- Kafka Consumers
- Azure Service Bus
- RabbitMQ
- Domain Events
- Integration Events

---

# External Entry Points

Document

- Webhooks
- Public APIs
- Scheduled Integrations
- File Imports

---

# Facts

Examples

- Repository contains 42 API endpoints.
- Three Hosted Services.
- One Kafka consumer.
- Four scheduled jobs.

Facts should be directly observable.

---

# Observations

Examples

- Controllers are thin.
- Business logic centralised.
- Queue consumers bypass services.
- Multiple entry points duplicate validation.

---

# Recommendations

Examples

- Consolidate duplicated entry points.
- Standardise authentication.
- Introduce shared validation.

Recommendations should preserve repository behaviour.

---

# Risks

Examples

- Unauthenticated endpoints.
- Duplicate routing.
- Long-running background jobs.
- Missing retries.

Classify

Low

Medium

High

---

# Questions Raised

Examples

- Are all scheduled jobs still active?
- Is every queue consumer still used?
- Can duplicate endpoints be consolidated?

---

# Assumptions

Document assumptions made during discovery.

If uncertain

```
Requires Human Confirmation
```

---

# References

Related Repository Context

- architecture.md
- projects.md
- repository.md
- database.md

Related Runtime Context

- capabilities.md
- runtime-flow.md

---

# Last Generated

Generated

Repository Commit

Generator

---

# Confidence

High

Medium

Low

Explain uncertainty.

---

# Success Criteria

✓ Every entry point identified

✓ Controllers documented

✓ Background services documented

✓ Queue consumers documented

✓ Scheduled jobs documented

✓ Business capabilities referenced

✓ Database usage identified

✓ Facts recorded

✓ Observations recorded

✓ Recommendations recorded

✓ Risks documented

✓ Questions Raised documented

✓ Confidence assessed
