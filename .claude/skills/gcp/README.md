# GCP Skill

## Purpose
Guide GCP-specific platform patterns used by TRS Platform golden paths and control-plane integrations.

## When to use
Use for work items involving GCP projects, IAM, networking, GKE, serverless, storage, or managed-service integration.

## Inputs expected from a Plane work item
- GCP services and environments in scope
- Project, folder, and region boundaries
- Security, networking, and compliance constraints
- Runtime and CI/CD dependencies

## Output contract
- GCP-specific design or implementation guidance
- Required IAM, networking, and provisioning considerations
- Validation expectations for policy, deployment, and operations

## Guardrails
- Keep GCP choices aligned with reusable platform abstractions
- Respect customer-managed projects and credentials
- Ensure tenant isolation, policy, and audit requirements remain explicit

## Definition of done
- [ ] GCP scope and services are identified
- [ ] IAM and network assumptions are clear
- [ ] Tenant and policy constraints are covered
- [ ] Runtime and pipeline dependencies are captured
- [ ] Validation path is documented
