# Kubernetes Skill

## Purpose
Guide runtime deployment patterns for Kubernetes-based golden paths and platform services.

## When to use
Use for work items affecting manifests, Helm charts, platform policies, workload configuration, ingress, or cluster operational concerns.

## Inputs expected from a Plane work item
- Runtime target (AKS, EKS, GKE, OpenShift, generic Kubernetes)
- Workload requirements, dependencies, and environment constraints
- Security, networking, observability, and approval requirements
- Operational expectations such as scaling, rollout, and rollback

## Output contract
- Runtime configuration plan or manifest updates
- Required policy, secret, and observability integrations
- Notes on deployment validation and operational readiness

## Guardrails
- Keep workloads tenant-safe and policy-compliant
- Avoid cluster-specific assumptions in shared abstractions unless the work item requires them
- Ensure secrets, identity, and network controls are explicit

## Definition of done
- [ ] Runtime target is explicit
- [ ] Deployment and policy requirements are covered
- [ ] Observability and security hooks are included
- [ ] Rollout/rollback considerations are documented
- [ ] Validation plan is identified
