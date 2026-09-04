# DevSecOps Skill

## Purpose
Guide secure-by-default delivery controls across CI/CD, dependencies, containers, infrastructure, and supply chain workflows.

## When to use
Use for work items that add or modify security scanning, policy gates, artifact integrity, release controls, or remediation workflows inside golden paths.

## Inputs expected from a Plane work item
- Required pipeline stages and security controls
- Target artifact types (code, containers, IaC, SBOMs)
- Compliance, approval, and exception requirements
- Expected pass/fail behavior and reporting needs

## Output contract
- Security gate design or implementation updates
- Required scanner, policy, and attestation touchpoints
- Validation steps for pipeline enforcement and remediation feedback

## Guardrails
- Do not weaken default security gates to satisfy delivery speed
- Keep exceptions explicit, auditable, and approval-driven
- Ensure outputs align with tenant boundaries and secrets handling rules

## Definition of done
- [ ] Required security controls are mapped
- [ ] Policy and exception handling is explicit
- [ ] Artifact and supply-chain expectations are covered
- [ ] Validation steps are defined
- [ ] Results can be audited per tenant/project
