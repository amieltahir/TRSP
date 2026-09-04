# TRS Platform — AI Platform Engineer

## Overview

The AI Platform Engineer is Module 11 of TRS Platform. It provides AI workflow orchestration across the software delivery lifecycle so teams can embed assisted generation, review, remediation, and operational guidance into Golden Paths and platform operations.

TRS Platform follows a bring-your-own-AI (BYO-AI) model. Customers use their own AI providers, models, subscriptions, and billing accounts. TRS Platform integrates those services into governed workflows and **does not resell model tokens or subscriptions**.

## Core Capabilities

| Capability | Description |
|-----------|-------------|
| **Workflow Orchestration** | Coordinate AI-assisted steps across code, infrastructure, pipeline, documentation, and operations workflows |
| **Generation Assistance** | Support scaffold and implementation generation from approved templates and specifications |
| **Automated Review** | Analyse code and configuration for quality, security, and standards compliance |
| **Security Remediation Guidance** | Suggest fixes for findings raised by DevSecOps controls |
| **Context Assembly** | Provide the relevant repository, architecture, and work-item context to approved workflows |
| **Tool Integration** | Connect workflows to Git, CI/CD, infrastructure, documentation, and observability systems |
| **Approval and Audit Controls** | Record actions, enforce approvals, and keep sensitive operations under human control |

## BYO-AI Operating Model

The AI Platform Engineer capability is intentionally separate from model ownership:

- **Customer-owned providers** — customers select the AI providers, models, and account structure that match their security, cost, and residency requirements.
- **Customer-owned subscriptions and spend** — model billing remains with the customer; TRS Platform does not broker or resell tokens.
- **Platform-owned orchestration** — TRS Platform owns workflow execution, context handling, policy checks, audit, and integration into Golden Paths.
- **Policy-governed usage** — provider access, model eligibility, and workflow permissions are constrained by Security & Governance and Enterprise & Multi-Tenancy controls.

## AI Workflow Architecture

```
                    PLATFORM CONTROL PLANE
                             │
                    AI Workflow Orchestration
                             │
         ┌───────────────────┼────────────────────┐
         ▼                   ▼                    ▼
  Context Assembly     Policy & Guardrails   Tool Integrations
         │                   │                    │
         │                   │                    ├── Git providers
         │                   │                    ├── Developer Portal
         │                   │                    ├── CI/CD pipelines
         │                   │                    ├── Infrastructure tooling
         │                   │                    ├── Security scanners
         │                   │                    └── Observability stack
         └───────────────────┼────────────────────┘
                             │
                  Customer AI Gateway / Provider Layer
                             │
         ┌───────────────────┼────────────────────┐
         ▼                   ▼                    ▼
    Provider A          Provider B           Provider C
    Model Set           Model Set            Model Set
```

This architecture keeps orchestration and governance inside TRS Platform while allowing provider choice and model routing to remain under customer control.

## Customer Configuration Ownership

Customers are responsible for configuring the AI connectivity used by their tenants and projects. TRS Platform should expose configuration and policy surfaces for:

| Configuration Area | Ownership / Expectation |
|--------------------|-------------------------|
| **Provider endpoints** | Customer supplies the AI gateway or provider endpoints used by each tenant or project |
| **Credentials** | Customer-managed credentials are stored in the platform secrets store and never hardcoded in templates or workflows |
| **Model routing** | Customer administrators define approved model routing, fallback behaviour, and environment-specific choices |
| **Allowlists / denylists** | Per-tenant and per-project policy controls determine which providers and models are allowed for which workflows |
| **Usage policy** | Rate limits, cost controls, and data-handling rules are enforced according to customer policy |
| **Auditability** | TRS Platform records workflow execution, provider selection, approval decisions, and relevant operational metadata |

## Context Model

Before an AI workflow acts, it should assemble only the context required for the approved task:

1. `CLAUDE.md` — engineering standards and agent instructions (repository root)
2. `docs/product/roadmap.md` — product architecture and module definitions
3. Relevant `docs/architecture/` documents — system and module design
4. `docs/adr/` — architecture decisions
5. Assigned Plane work item — the specific task or story
6. Repository code and configuration — existing implementation

This keeps workflows aligned to product architecture, tenancy boundaries, and repository standards.

## AI Workflow Integration in Golden Paths

Every Golden Path may include approved AI workflow integration points such as:

- Review assistance on pull requests
- Security finding analysis and remediation guidance
- Dependency and upgrade recommendations
- Test coverage and quality feedback
- Documentation drafting within platform guardrails

The exact workflow set can vary by language, cloud, runtime, and tenant policy.

## Governance Constraints

AI-assisted workflows operate within the Security & Governance and Enterprise & Multi-Tenancy modules:

- All workflow actions are audit-logged with tenant, project, and actor context
- Workflows cannot bypass RBAC, tenant isolation, or platform policy checks
- Workflow-generated changes must pass the same DevSecOps and Testing & Quality gates as human-authored changes
- Sensitive operations such as production deployments, credential management, and policy exceptions require human approval
- Prompt, response, and execution records are retained according to tenant policy and data retention rules

## Provider and Model Selection

Provider and model selection should be governed by ADR and customer policy. Selection criteria include:

- Capability for the task type
- Data residency and regulatory requirements
- Cost, rate limits, and spend ownership
- Latency and availability requirements
- Security and privacy classification of the input data
- Tenant- or project-specific allowlists and approval requirements
