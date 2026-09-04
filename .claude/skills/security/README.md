# Security Skill

## Purpose
Guide repository, platform, tenant, and workflow security decisions across TRS Platform modules.

## When to use
Use for work items involving RBAC, tenant isolation, secrets management, policy enforcement, approvals, audit, compliance, or sensitive AI workflow controls.

## Inputs expected from a Plane work item
- Threats, constraints, or compliance objectives
- Resources, actors, and tenant boundaries in scope
- Sensitive operations and approval requirements
- Required evidence for audit or policy enforcement

## Output contract
- Security requirements or implementation guidance
- Required controls for auth, tenancy, secrets, and audit
- Notes on validation, exception handling, and residual risk

## Guardrails
- Never bypass RBAC, tenant isolation, or secrets-store policy
- Keep approvals mandatory for sensitive operations
- Treat customer AI credentials, gateways, and provider settings as protected configuration

## Definition of done
- [ ] Actors and boundaries are identified
- [ ] Required controls are explicit
- [ ] Secrets and approvals are handled correctly
- [ ] Audit/compliance expectations are covered
- [ ] Validation or review steps are documented
