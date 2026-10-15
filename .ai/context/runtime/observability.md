# Runtime Observability

---

# Purpose

This document describes how the application is monitored and observed at runtime.

Its purpose is to help engineers understand how application health, failures and runtime behaviour are detected, diagnosed and validated.

This document should answer

> "How do we know the application is behaving correctly?"

Observability provides the engineering evidence required to operate and validate the application.

---

# Scope

This document covers

- Logging
- Metrics
- Distributed Tracing
- Health Checks
- Monitoring
- Alerting
- Dashboards
- Diagnostics
- Operational visibility

This document does not describe implementation details.

---

# Observability Summary

Document

- Logging framework
- Metrics platform
- Tracing platform
- Health checks
- Alerting
- Dashboards

Summarise overall observability maturity.

---

# Logging

Document logging implementation.

Examples

- Serilog
- NLog
- log4net
- Microsoft.Extensions.Logging

Describe

- Log levels
- Structured logging
- Correlation IDs
- Exception logging
- Audit logging

---

# Metrics

Document runtime metrics.

Examples

- Request Count
- Request Duration
- Error Rate
- Queue Depth
- Background Job Duration
- Database Latency

Document where metrics are collected.

---

# Distributed Tracing

Document tracing capability.

Examples

- OpenTelemetry
- Application Insights
- Jaeger
- Zipkin

Describe

- Request tracing
- External dependency tracing
- Database tracing
- Queue tracing

---

# Health Checks

Document health endpoints.

Examples

- API Health
- Database Connectivity
- Queue Connectivity
- External API Connectivity

Describe

- Liveness
- Readiness
- Startup checks

---

# Monitoring

Document operational monitoring.

Examples

- Dashboards
- Infrastructure Monitoring
- Application Monitoring
- Scheduled Job Monitoring

---

# Alerting

Document alerts.

Examples

- Failed Jobs
- Database Connectivity
- Queue Failures
- High Error Rate
- Long Response Time

Describe alert ownership if known.

---

# Operational Dashboards

Document dashboards.

Examples

- Application Health
- Business Metrics
- Synchronization Status
- Queue Status
- API Performance

---

# Diagnostic Capability

Assess runtime diagnostics.

Examples

- Correlation IDs
- Structured Logs
- Exception Details
- Request Replay
- Audit Trails

---

# Migration Observability

Assess readiness for modernization.

Examples

- Oracle query timing available
- PostgreSQL comparison possible
- Integration latency measurable
- Business capability metrics available

Document gaps that may affect migration validation.

---

# Facts

Record verified facts.

Examples

- Serilog configured centrally.
- Application exposes /health endpoint.
- SQL execution time logged.
- Background jobs emit metrics.

Facts should be directly observable.

---

# Observations

Examples

- Logging consistent across APIs.
- No distributed tracing.
- Background jobs lack monitoring.
- Database metrics incomplete.

Observations should be evidence-based.

---

# Recommendations

Examples

- Adopt OpenTelemetry.
- Standardise structured logging.
- Add health checks for integrations.
- Instrument PostgreSQL queries during migration.

Recommendations should preserve runtime behaviour.

---

# Risks

Examples

- Missing diagnostics
- No tracing
- Poor log quality
- Missing alerts
- Limited production visibility

Classify

- Low
- Medium
- High

---

# Questions Raised

Examples

- Can Oracle and PostgreSQL performance be compared?
- Are business capabilities observable independently?
- Are failures traceable end-to-end?
- Is production telemetry sufficient for migration?

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

- build.md
- testing.md

Runtime Context

- runtime-flow.md
- integrations.md
- operations.md
- data-flow.md

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

✓ Logging documented

✓ Metrics documented

✓ Tracing documented

✓ Health checks documented

✓ Monitoring documented

✓ Alerting documented

✓ Dashboards documented

✓ Migration observability assessed

✓ Facts recorded

✓ Observations recorded

✓ Recommendations recorded

✓ Risks documented

✓ Questions Raised documented

✓ Assumptions documented

✓ Confidence assessed
