# GitHub Copilot Instructions

- Understand before modifying.
- Preserve existing behavior.
- AI assists; humans approve.
- Prefer incremental, reviewable changes.
- Use issue-driven orchestration via `.github/ISSUE_TEMPLATE/*.yml`.
- Do discovery before specs, and specs before planning/implementation.
- Use repository knowledge first: `.ai/context/repository/` and `.ai/context/runtime/`.
- Use canonical specification path: `.ai/specifications/<spec-id>/`.
- Follow applicable standards in `.ai/playbooks/` (especially `modernization/` and `oracle-to-postgresql/`).
- Do not expand scope silently; escalate as `Requires Human Confirmation`.
- Never guess unknowns; write `Unknown` when evidence is missing.
- Update documentation when behavior, configuration, testing, or deployment expectations change.