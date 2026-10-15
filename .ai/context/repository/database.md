# Database Usage

---

# Purpose

This document describes how the repository interacts with databases.

Its purpose is to identify database technologies, access patterns, dependencies and migration scope.

This document should answer

> "How does this repository use the database?"

It should not redesign database schema.

Schema design decisions belong outside Repository Context.

Shared schema input artifacts for Oracle → PostgreSQL work may be stored under

```
.ai/context/repository/database/
```

and referenced from this document.

---

# Scope

This document covers

- Database technologies
- Database clients
- Data access patterns
- ORM usage
- Repository implementations
- SQL usage
- Database objects
- Transactions
- Migration impact

This document does not describe business behaviour.

---

# Database Summary

## Primary Database

Examples

- Oracle
- PostgreSQL
- SQL Server

---

## Secondary Databases

Document additional databases if applicable.

---

## Database Technologies

Examples

- Oracle.ManagedDataAccess

- Npgsql

- Dapper

- Entity Framework

- ADO.NET

---

# Database Access Strategy

Describe how the repository accesses data.

Examples

- Repository Pattern

- Dapper

- Entity Framework

- Raw SQL

- Stored Procedures

- Mixed Approach

---

# Database Clients

Document every database client.

Example

| Client                   | Usage             | Projects       |
| ------------------------ | ----------------- | -------------- |
| Oracle.ManagedDataAccess | Oracle access     | Infrastructure |
| Npgsql                   | PostgreSQL access | None           |

---

# Repository Inventory

Document every repository that performs database access.

For each repository record

## Repository

Name

Purpose

Database

Primary Tables

Views

Stored Procedures

Functions

Sequences

Inline SQL

Transaction Usage

Consumers

---

# SQL Usage

Identify

- Inline SQL
- SQL Files
- Dynamic SQL

Document

- Location
- Purpose
- Complexity

---

# Stored Procedures

Document

- Procedure Name

- Calling Repository

- Purpose

- Input Parameters

- Output

- Business Capability

---

# Views

Document

- View Name

- Purpose

- Calling Repository

- Business Capability

---

# Functions

Document

- Function Name

- Purpose

- Calling Repository

- Business Capability

---

# Sequences

Document

- Sequence Name

- Usage

- Consumers

---

# Transactions

Describe transaction strategy.

Examples

- TransactionScope

- DbTransaction

- OracleTransaction

- Unit of Work

Document transaction ownership.

---

# Oracle Dependencies

Identify Oracle-specific implementation.

Examples

- OracleConnection

- OracleCommand

- OracleParameter

- OracleTransaction

- OracleException

- OracleBulkCopy

Document where each dependency exists.

---

# PostgreSQL Readiness

Assess repository readiness.

Examples

- Oracle isolated behind repositories

- Oracle usage concentrated

- SQL mostly portable

- Heavy Oracle-specific implementation

---

# Migration Impact

Identify migration impact.

Examples

- Client replacement

- SQL translation

- Stored Procedure translation

- View translation

- Function translation

- Configuration

- Testing

Do not estimate implementation effort.

---

# Facts

Record verified facts.

Examples

- Repository uses Oracle.ManagedDataAccess.

- 47 repositories access Oracle.

- 83 inline SQL statements detected.

- 14 stored procedures referenced.

---

# Observations

Document engineering observations.

Examples

- Oracle access isolated.

- SQL heavily duplicated.

- Dynamic SQL widespread.

- Transactions inconsistent.

---

# Recommendations

Examples

- Replace Oracle client with Npgsql.

- Consolidate duplicated SQL.

- Move inline SQL into repositories.

- Reduce Oracle-specific APIs.

Recommendations should preserve repository behaviour.

---

# Risks

Examples

- Heavy Oracle coupling

- Dynamic SQL

- Complex transactions

- Oracle-specific packages

- Missing integration tests

Classify

Low

Medium

High

---

# Questions Raised

Examples

- Are all stored procedures still active?

- Can Dapper replace OracleCommand?

- Are all views required?

- Can TransactionScope remain unchanged?

---

# Assumptions

Examples

- Oracle schema available.

- PostgreSQL schema translated manually.

- Database objects current.

If uncertain

record

```
Requires Human Confirmation
```

---

# References

Related Repository Context

- repository.md
- architecture.md
- dependencies.md
- testing.md

Related Standards

- Oracle → PostgreSQL
- Translation Rules

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

Explain any uncertainty.

---

# Success Criteria

✓ Database technologies documented

✓ Database access strategy documented

✓ Database clients identified

✓ Repository inventory completed

✓ SQL usage identified

✓ Stored Procedures documented

✓ Views documented

✓ Functions documented

✓ Sequences documented

✓ Transactions documented

✓ Oracle dependencies identified

✓ PostgreSQL readiness assessed

✓ Migration impact documented

✓ Facts recorded

✓ Observations recorded

✓ Recommendations recorded

✓ Risks documented

✓ Questions Raised documented

✓ Assumptions documented

✓ Confidence assessed
