# Build

---

# Purpose

This document describes how the repository is built, validated and packaged.

Its purpose is to provide engineers and AI agents with a complete understanding of the repository build process before implementation begins.

This document should answer

> "How do I successfully build and validate this repository?"

It should not describe deployment architecture.

---

# Scope

This document covers

- Build tools
- SDK requirements
- Build configuration
- Package restore
- Build outputs
- CI integration
- Local development workflow
- Validation commands

Deployment pipelines are documented separately.

---

# Build Summary

Document

- Build system
- Target framework(s)
- SDK requirements
- Package manager
- CI platform

---

# Repository Build

Describe how the repository is built.

Examples

- Visual Studio Solution
- dotnet CLI
- MSBuild
- Cake
- Nuke

Document the recommended build entry point.

---

# SDK Requirements

Document

- .NET SDK
- Visual Studio Version
- Node.js
- Java
- Other required tooling

Examples

- .NET Framework 4.8 Developer Pack
- .NET SDK 8.0
- Node.js 22 LTS

---

# Package Management

Document

- NuGet
- npm
- yarn
- pnpm
- Maven

Identify package restore commands.

---

# Build Commands

Document the canonical commands.

Examples

```bash
dotnet restore

dotnet build

dotnet test
```

or

```powershell
msbuild Solution.sln
```

Prefer the simplest reproducible workflow.

---

# Build Configuration

Document

- Debug
- Release
- Any custom configurations

Describe when each configuration is used.

---

# Generated Outputs

Document

Examples

- DLLs
- NuGet Packages
- Docker Images
- Published Artifacts

---

# Continuous Integration

Document

- GitHub Actions
- Azure DevOps
- Jenkins
- TeamCity

Reference workflow files where applicable.

Do not duplicate pipeline definitions.

---

# Local Development

Document the recommended workflow.

Examples

Restore

↓

Build

↓

Run Tests

↓

Run Application

↓

Validate

This becomes the default workflow for Developer Agent.

---

# Validation

Document the minimum validation expected before opening a Pull Request.

Examples

- Restore succeeds
- Build succeeds
- Tests pass
- No analyzer warnings
- Formatting passes

---

# Build Dependencies

Reference

- dependencies.md
- projects.md

Do not duplicate dependency information.

---

# Facts

Examples

- Repository uses MSBuild.
- GitHub Actions executes Release builds.
- dotnet test runs all test projects.
- npm required for Angular frontend.

Facts should be directly observable.

---

# Observations

Examples

- Multiple build entry points.
- Build scripts duplicated.
- Manual build steps required.
- Legacy tooling still required.

---

# Recommendations

Examples

- Standardise build entry point.
- Upgrade SDK.
- Remove duplicate scripts.
- Introduce reproducible local builds.

Recommendations should preserve repository behaviour.

---

# Risks

Examples

- Unsupported SDK
- Manual build steps
- Missing lock files
- Inconsistent build configurations

Classify

Low

Medium

High

---

# Questions Raised

Examples

- Can the repository migrate to dotnet CLI only?
- Are all build scripts still required?
- Can package restore be simplified?
- Can CI and local builds be aligned?

---

# Assumptions

Document assumptions made during discovery.

Examples

- Build not executed.
- CI workflow inferred from repository.
- Local prerequisites not validated.

If uncertain

record

```
Requires Human Confirmation
```

---

# References

Related Repository Context

- repository.md
- dependencies.md
- projects.md

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

✓ Build system documented

✓ SDK requirements documented

✓ Package management documented

✓ Build commands documented

✓ Build configuration documented

✓ Generated outputs documented

✓ CI integration documented

✓ Local development workflow documented

✓ Validation process documented

✓ Facts recorded

✓ Observations recorded

✓ Recommendations recorded

✓ Risks documented

✓ Questions Raised documented

✓ Assumptions documented

✓ Confidence assessed
