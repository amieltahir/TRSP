# Golden Path Iteration Playbook

## Purpose
Provide a repeatable rollout model for iterating TRS Platform golden paths across Language × Cloud × Runtime combinations.

## Rollout waves

1. **Reference wave** — establish one opinionated baseline for a priority language on a primary cloud/runtime (for example Java × Azure × Kubernetes).
2. **Language expansion wave** — add additional languages on the same cloud/runtime once shared controls are proven.
3. **Runtime expansion wave** — add alternative runtimes such as serverless or OpenShift using the same platform contracts.
4. **Cloud expansion wave** — port proven language/runtime patterns to AWS and GCP.
5. **Optimisation wave** — improve observability, security posture, AI workflow options, and commercial controls without breaking contracts.

## Inputs expected from a Plane work item
- Target language, cloud, and runtime
- Owning module(s) and dependencies
- Required developer experience outcomes
- Tenant, security, compliance, and approval constraints
- Success metrics and rollout scope

## Quality gates

- **Architecture gate** — module ownership, ADR needs, and control-plane contracts are clear.
- **Template gate** — scaffolding inputs, output structure, and documentation are stable.
- **Infrastructure gate** — reusable provisioning modules exist with tenant-safe configuration boundaries.
- **CI/CD gate** — build, test, security, and deploy workflows are defined.
- **DevSecOps gate** — SAST, SCA, container, IaC, and supply-chain controls are enabled where applicable.
- **Observability gate** — metrics, logs, traces, and baseline alerts are included.
- **Testing & Quality gate** — unit, integration, end-to-end, and conformance requirements are identified.
- **AI workflow gate** — any AI-assisted steps use customer-managed providers, approved models, audit logging, and human approvals for sensitive actions.

## Promotion criteria

A golden path is ready to promote when:

- The language × cloud × runtime contract is documented and versioned.
- Required templates, infrastructure modules, pipelines, and runtime assets are implemented or explicitly planned.
- Security, tenant isolation, and compliance controls are embedded by default.
- Validation evidence exists for the agreed quality gates.
- Documentation is sufficient for onboarding, operation, and support.
- Rollback, deprecation, and upgrade expectations are defined.

## Output contract

- Recommended rollout wave and rationale
- Dependency map across modules
- Gate status or missing prerequisites
- Promotion decision: design, implement, test, promote, maintain, or defer

## Guardrails

- Prioritise repeatable factory patterns over one-off customisations.
- Keep platform governance stronger than convenience shortcuts.
- Treat AI workflow integration as governed augmentation, not as the product itself.
- Never require TRS Platform to own customer provider subscriptions or token billing.

## Definition of done

- [ ] Rollout wave is assigned
- [ ] Quality gates are evaluated
- [ ] Promotion criteria are checked
- [ ] Dependencies and blockers are explicit
- [ ] Next-step recommendation is documented
