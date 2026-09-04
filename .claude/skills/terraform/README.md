# Terraform Skill

## Purpose
Guide reusable infrastructure module design and golden-path provisioning patterns.

## When to use
Use for work items involving Terraform modules, environment composition, variable contracts, state considerations, or cloud resource provisioning.

## Inputs expected from a Plane work item
- Target cloud, environment, and runtime
- Required resources and shared module dependencies
- Tenant/project scoping rules and secret requirements
- Validation expectations for plan, apply, and policy checks

## Output contract
- Module structure or change plan
- Input/output contract with tenant-aware parameters
- Notes on policy, CI/CD, and observability dependencies

## Guardrails
- Keep modules reusable and cloud-account safe
- Never hardcode credentials or environment secrets
- Preserve policy and tagging/metadata requirements for tenancy and audit

## Definition of done
- [ ] Module inputs/outputs are defined
- [ ] Tenant/project metadata is accounted for
- [ ] Security and policy checks are identified
- [ ] Runtime and pipeline dependencies are captured
- [ ] Validation approach is documented
