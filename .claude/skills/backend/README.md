# Backend Skill

## Purpose
Guide backend implementation for platform APIs, orchestration services, workflow execution, and provider integrations.

## When to use
Use for work items affecting the Platform Control Plane, service APIs, persistence, eventing, or backend workflow logic behind golden paths.

## Inputs expected from a Plane work item
- API or workflow requirements
- Domain entities and tenant context requirements
- Integration points with CI/CD, infra, AI workflows, or external systems
- Validation and non-functional requirements

## Output contract
- Backend design or code changes aligned to the control-plane contract
- Validation approach for API, workflow, and auth behavior
- Notes on required events, audits, or provider abstractions

## Guardrails
- Enforce authentication, authorisation, and tenant scoping on every path
- Store secrets only in the platform secrets store
- Avoid provider-specific leakage into shared platform contracts

## Definition of done
- [ ] API/workflow contract is defined
- [ ] Tenant and RBAC checks are covered
- [ ] Integration side effects are audit-ready
- [ ] Validation plan covers happy path and policy failures
- [ ] Output matches the assigned module scope
