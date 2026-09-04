# Claude Skills for TRS Platform

## Purpose

This directory routes Claude and other coding agents to the right skill guidance when implementing Plane work items for TRS Platform golden paths and platform modules.

## When to use

Use this index before starting implementation when a work item spans architecture, application code, cloud infrastructure, runtime configuration, security, testing, or observability.

## Inputs expected from a Plane work item

- Module and work-item title
- Problem statement and acceptance criteria
- Language, cloud, and runtime targets
- Tenant, security, and compliance constraints
- Required deliverables and validation gates

## Skill router

| Skill | Use when the work item is mainly about |
|-------|----------------------------------------|
| [architecture](architecture/README.md) | module boundaries, ADRs, control-plane contracts, cross-module design |
| [backend](backend/README.md) | APIs, orchestration, workflow services, persistence, integrations |
| [frontend](frontend/README.md) | Backstage UX, forms, portal components, TechDocs-facing flows |
| [golden-paths](golden-paths/README.md) | language × cloud × runtime compositions and rollout sequencing |
| [devsecops](devsecops/README.md) | security gates, CI/CD controls, supply-chain automation |
| [terraform](terraform/README.md) | reusable infrastructure modules and environment provisioning |
| [kubernetes](kubernetes/README.md) | runtime manifests, Helm, policies, workload operations |
| [azure](azure/README.md) | Azure landing zones, managed services, identity, networking |
| [aws](aws/README.md) | AWS platform patterns, IAM, networking, managed services |
| [gcp](gcp/README.md) | GCP platform patterns, IAM, networking, managed services |
| [testing](testing/README.md) | test strategy, conformance, evaluation, quality gates |
| [observability](observability/README.md) | metrics, logs, traces, SLOs, operational visibility |
| [security](security/README.md) | RBAC, tenant isolation, secrets, policy, approvals, compliance |

## Output contract

The selected skill should produce implementation guidance or changes that are traceable to the Plane work item, compatible with the canonical 16-module taxonomy, and safe for tenant-aware platform delivery.

## Guardrails

- Keep TRS Platform positioned as an Internal Developer Platform, not as a token reseller or standalone agent product.
- Preserve the canonical 16-module ordering and naming.
- Enforce tenant context, RBAC, secrets-store usage, and human approvals for sensitive operations.
- Avoid speculative features; implement only what the Plane work item requests.

## Definition of done

- [ ] Correct skill guidance selected for the work item
- [ ] Inputs from the Plane item are captured before implementation starts
- [ ] Deliverables map to the owning TRS Platform module(s)
- [ ] Security, multi-tenancy, and compliance guardrails are respected
- [ ] Validation steps and promotion criteria are identified
