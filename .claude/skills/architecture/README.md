# Architecture Skill

## Purpose
Guide architecture-grade changes across TRS Platform modules, interfaces, and ADR-driven decisions.

## When to use
Use for work items that change module boundaries, control-plane responsibilities, data contracts, integration patterns, or golden-path composition rules.

## Inputs expected from a Plane work item
- Owning module and related modules
- Problem statement, constraints, and acceptance criteria
- Required tenant, security, and compliance boundaries
- Existing ADRs or architecture docs that constrain the solution

## Output contract
- Updated architecture docs, diagrams, and module responsibilities
- ADR recommendation when the change is significant
- Clear contract assumptions for downstream backend, frontend, and platform work

## Guardrails
- Preserve the canonical 16-module taxonomy
- Keep RBAC, tenant isolation, and audit boundaries explicit
- Do not invent capabilities beyond the approved Plane scope

## Definition of done
- [ ] Module ownership is clear
- [ ] Cross-module interactions are documented
- [ ] Tenant and security constraints are explicit
- [ ] ADR need is assessed
- [ ] Documentation is implementation-safe
