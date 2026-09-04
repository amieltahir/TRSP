# AWS Skill

## Purpose
Guide AWS-specific platform patterns used by TRS Platform golden paths and control-plane integrations.

## When to use
Use for work items involving AWS accounts, IAM, networking, EKS, serverless, storage, or managed-service integration.

## Inputs expected from a Plane work item
- AWS services and environments in scope
- Account, region, and boundary requirements
- Security, networking, and compliance constraints
- Runtime and CI/CD dependencies

## Output contract
- AWS-specific design or implementation guidance
- Required IAM, networking, and provisioning considerations
- Validation expectations for policy, deployment, and operations

## Guardrails
- Keep AWS choices aligned with reusable platform abstractions
- Respect customer-managed accounts and credentials
- Ensure tenant isolation, policy, and audit requirements remain explicit

## Definition of done
- [ ] AWS scope and services are identified
- [ ] IAM and network assumptions are clear
- [ ] Tenant and policy constraints are covered
- [ ] Runtime and pipeline dependencies are captured
- [ ] Validation path is documented
