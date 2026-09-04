# Observability Skill

## Purpose
Guide metrics, logs, traces, and SLO-aware operational visibility for platform services and golden paths.

## When to use
Use for work items affecting telemetry standards, dashboards, alerting, tracing, audit visibility, or operational feedback loops.

## Inputs expected from a Plane work item
- Services, workflows, or golden paths in scope
- Required signals, dashboards, and alerts
- Tenant-aware visibility and retention constraints
- Operational objectives or SLO expectations

## Output contract
- Observability requirements or implementation guidance
- Required metrics, logs, traces, and alert hooks
- Notes on audit, tenancy, and runtime dependencies

## Guardrails
- Keep telemetry aligned with tenant isolation and data-retention policy
- Capture enough context for operations without exposing secrets or restricted data
- Ensure signals support both platform teams and golden-path consumers

## Definition of done
- [ ] Required telemetry signals are identified
- [ ] Alert/SLO expectations are clear
- [ ] Tenant-aware visibility constraints are respected
- [ ] Runtime and pipeline dependencies are captured
- [ ] Operational validation is defined
