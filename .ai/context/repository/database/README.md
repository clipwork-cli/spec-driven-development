# Shared Schema Inputs

Use this directory for shared schema artifacts consumed by Oracle → PostgreSQL specifications.

Recommended files:

- schema.sql
- constraints.sql
- foreign-keys.sql
- indexes.sql
- views.sql
- functions.sql

Guidance:

- Store cross-capability schema inputs here.
- Keep capability-specific schema inputs under `.ai/specifications/<spec-id>/schema/`.
- Reference consumed files from the Specification issue and `specification.md`.
- Do not redesign schema here; use engineer-provided target schema artifacts.
