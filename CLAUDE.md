# CLAUDE.md — TRS Platform Engineering Agent Instructions

This file is read by Claude Code and other AI engineering agents before making any changes to this repository.

## What is TRS Platform?

TRS Platform is an Internal Developer Platform (IDP). It provides developer experience capabilities, golden paths, AI-assisted engineering workflow orchestration, and fully automated DevSecOps pipelines.

**The product is called TRS Platform.** Do not use "Aurex" as the product name.

Customers bring their own AI providers, models, subscriptions, and gateway connectivity. TRS Platform orchestrates workflows and governance around those integrations and does not resell model tokens.

## Before You Start

Always read these documents before making any implementation changes:

1. **This file** (`CLAUDE.md`) — agent instructions and engineering standards
2. [`docs/product/roadmap.md`](docs/product/roadmap.md) — 16-module product structure
3. [`docs/product/product-map.md`](docs/product/product-map.md) — one-page mental model
4. [`docs/architecture/system-architecture.md`](docs/architecture/system-architecture.md) — system design
5. The relevant `docs/architecture/` document for the module you are working on
6. [`docs/engineering/test-strategy.md`](docs/engineering/test-strategy.md) — testing strategy and quality standards
7. The assigned Plane work item — the specific story or task

## Module Structure

TRS Platform has exactly 16 product modules:

| # | Module |
|---|--------|
| 01 | Product & Architecture |
| 02 | Platform Control Plane |
| 03 | Developer Portal |
| 04 | Template Engine |
| 05 | Golden Paths |
| 06 | Infrastructure Automation |
| 07 | CI/CD |
| 08 | DevSecOps |
| 09 | Security & Governance |
| 10 | Observability |
| 11 | AI Platform Engineer |
| 12 | Enterprise & Multi-Tenancy |
| 13 | Commercialisation |
| 14 | Documentation |
| 15 | Testing & Quality |
| 16 | Cloud Native & Runtime |

Do not create new modules. If you believe a new module is needed, raise it as a product discussion — do not implement it unilaterally.

## Engineering Rules

### General

- Implement only what is described in the assigned Plane work item
- Do not implement speculative features or gold-plate solutions
- Follow existing patterns in the codebase
- All code must be tested
- All code must pass DevSecOps gates

### Multi-Tenancy

Every resource must carry tenant context:

```json
{
  "organisation_id": "...",
  "tenant_id": "...",
  "project_id": "...",
  "created_by": "..."
}
```

Do not create resources without tenant context.

### Security

- Never hardcode credentials, tokens, or secrets
- All secrets must be stored in the platform secrets store
- All API endpoints must enforce authentication and authorisation
- RBAC is enforced at the Platform Control Plane layer — do not bypass it

### Architecture Decisions

If you make a significant architectural decision (technology choice, API design, data model), emit an ADR in `docs/adr/` using the template in `docs/adr/README.md`.

### Commit Messages

Use conventional commits:

```
feat(module): short description
fix(module): short description
docs(module): short description
chore: short description
```

Where `module` is the short name of the relevant TRS Platform module.

## Source of Truth

| Source | Purpose |
|--------|---------|
| GitHub | Product vision, architecture, standards, ADRs |
| Plane | Modules, epics, features, stories, tasks, sprints |
| Claude Code | Implementation |
| Git | Record of what changed |

## What NOT to Do

- Do not rename or reorganise the 16 modules
- Do not use "Aurex" as the product name
- Do not implement features not in the assigned Plane work item
- Do not bypass RBAC or tenant isolation
- Do not hardcode secrets
- Do not create helper scripts or workarounds — use standard platform tooling
- Do not commit code that fails tests or security gates
