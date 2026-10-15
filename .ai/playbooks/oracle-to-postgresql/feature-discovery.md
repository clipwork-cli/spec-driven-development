# Feature Discovery Standard

**Version:** 1.0

---

# Purpose

This document defines how engineering work should be decomposed during an Oracle to PostgreSQL migration.

Unlike traditional migrations that organise work by architectural layer, Spec-driven Development organises migration work by **Business Capability**.

The objective is that every completed Specification delivers a working, independently testable slice of functionality.

---

# Philosophy

Migration work should follow Vertical Slice Architecture.

Avoid organising work by

- Controllers
- Services
- Repositories
- Database
- Infrastructure

Instead organise work by

Business Capability.

Each capability should contain everything required for successful migration.

---

# Discovery Workflow

The Architect should perform discovery in the following order.

```
Read Repository Context

↓

Read Runtime Context

↓

Identify Business Capabilities

↓

Locate Entry Points

↓

Trace Execution Flow

↓

Locate Database Usage

↓

Determine Migration Unit

↓

Generate Specification
```

---

# Business Capability

A Business Capability represents a complete business function delivered by the application.

Examples

- Search Assets
- Register Asset
- Create Work Order
- Generate Report
- Import Data

Capabilities should be understandable by business users.

Avoid technical names.

---

# Migration Unit

One Business Capability equals one Migration Unit.

Each Migration Unit should produce

```
feature.md

spec.md

decision-log.md
```

Every Migration Unit should be independently

- understandable
- implementable
- reviewable
- testable

---

# Capability Discovery

When identifying capabilities

look for

- Controllers
- API Endpoints
- Background Jobs
- Scheduled Tasks
- Queue Consumers
- UI Entry Points

Trace each execution path.

---

# Capability Boundary

A capability should contain everything required to preserve behaviour.

Typical components include

- Controllers
- Services
- Domain Logic
- Repositories
- Database Objects
- Integration Points
- Tests

Do not split these across different Specifications.

---

# Database Discovery

For every capability identify

- Tables
- Views
- Stored Procedures
- Functions
- Packages
- Sequences
- Synonyms
- Inline SQL

These become dependencies of the capability.

---

# SQL Discovery

Identify

Inline SQL

Examples

- Dapper
- ADO.NET
- Repository SQL
- Dynamic SQL

Document

- location
- purpose
- affected tables

---

# Stored Procedure Discovery

For every stored procedure determine

- Purpose
- Calling location
- Input parameters
- Output
- Tables accessed
- Dependencies

Stored procedures should migrate together with the capability that owns them.

---

# View Discovery

Document

- View Name
- Calling Location
- Purpose
- Referenced Tables
- Oracle Functions Used

Views should migrate together with their owning capability.

---

# Repository Discovery

Document

- Repository Class
- Methods
- SQL
- Oracle Client Usage
- Transactions

Repositories are implementation details.

They do not define migration boundaries.

---

# Entry Point Discovery

Identify

- API
- Controller
- Background Job
- Queue Consumer
- Scheduled Task
- Event Handler

Every capability must have at least one entry point.

---

# Dependency Discovery

For each capability identify

Application Dependencies

- Services
- Repositories
- Shared Libraries

Database Dependencies

- Tables
- Views
- Procedures
- Functions

External Dependencies

- APIs
- Queues
- Files
- Storage

---

# Manual Activities

Identify work that AI cannot complete.

Examples

- PostgreSQL Schema Creation
- Data Migration
- Production Cutover
- Infrastructure Changes

Document these under

Manual Activities

inside the Specification.

---

# Capability Complexity

Classify each capability

Low

Medium

High

Consider

- Database complexity
- Number of objects
- External integrations
- Business risk

High complexity capabilities should be split only when they remain independently testable.

---

# Specification Generation

Each capability should produce

```
Feature

↓

Specification

↓

Decision Log
```

Specifications should describe

- Business objective
- Scope
- Acceptance Criteria
- Database Objects
- Manual Activities
- Risks
- Success Criteria

Implementation belongs to the Planner.

---

# Success Criteria

Feature Discovery is complete when

✓ Every business capability has been identified

✓ Every entry point has been traced

✓ Every Oracle dependency has been identified

✓ Every database object has an owning capability

✓ Every capability is independently testable

✓ Every capability can produce one Specification
