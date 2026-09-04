# Azure Skill

## Purpose
Guide Azure-specific platform patterns used by TRS Platform golden paths and control-plane integrations.

## When to use
Use for work items involving Azure landing zones, identity, networking, AKS, serverless, storage, or managed-service integration.

## Inputs expected from a Plane work item
- Azure services and environments in scope
- Subscription, tenant, and resource-group boundaries
- Security, networking, and compliance constraints
- Runtime and CI/CD dependencies

## Output contract
- Azure-specific design or implementation guidance
- Required identity, networking, and provisioning considerations
- Validation expectations for policy, deployment, and operations

## Guardrails
- Keep Azure choices aligned with reusable platform abstractions
- Respect customer-managed subscriptions and credentials
- Ensure tenant isolation, policy, and audit requirements remain explicit

## Definition of done
- [ ] Azure scope and services are identified
- [ ] Identity and network assumptions are clear
- [ ] Tenant and policy constraints are covered
- [ ] Runtime and pipeline dependencies are captured
- [ ] Validation path is documented
