# Testing Skill

## Purpose
Guide validation strategy for platform code, golden paths, contracts, integrations, and AI-assisted workflows.

## When to use
Use for work items that define or change unit, integration, end-to-end, conformance, or evaluation requirements.

## Inputs expected from a Plane work item
- Acceptance criteria and risk areas
- Layers that must be validated
- Required local, CI, and expensive-environment test coverage
- Quality gates and promotion expectations

## Output contract
- Test plan mapped to the repository testing strategy
- Required deterministic and higher-order validation layers
- Evidence expectations for promotion or release readiness

## Guardrails
- Prefer fast deterministic tests first
- Keep expensive cloud/runtime validation scoped and intentional
- Ensure AI workflow behavior is evaluated like any other platform capability

## Definition of done
- [ ] Relevant test layers are identified
- [ ] Deterministic validation is prioritised
- [ ] CI and higher-environment needs are explicit
- [ ] Pass/fail evidence is defined
- [ ] Quality-gate impact is documented
