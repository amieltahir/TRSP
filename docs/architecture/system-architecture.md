# TRS Platform — System Architecture

## Overview

TRS Platform is an Internal Developer Platform composed of 16 product modules. This document describes the high-level system architecture, component boundaries, and integration points.

## Conceptual Architecture

```
                     ┌─────────────────────┐
                     │      BACKSTAGE      │
                     │  Developer Portal    │
                     └──────────┬──────────┘
                                │  REST / gRPC / Events
                                ▼
                ┌───────────────────────────┐
                │      TRS PLATFORM         │
                │                           │
                │    Platform Control Plane │
                │    ├── Platform APIs      │
                │    ├── Orchestration      │
                │    ├── Workflow Engine    │
                │    └── Audit & Events     │
                └─────────────┬─────────────┘
                              │
         ┌────────────────────┼────────────────────┐
         ▼                    ▼                    ▼
   Golden Paths          AI Engineer          DevSecOps
   ├── Templates         ├── Code Gen          ├── SAST
   ├── Scaffolding        ├── Review           ├── SCA
   └── Composition        ├── Remediation      ├── Container
                          └── Workflow         └── IaC
         │                    │                    │
         └────────────────────┼────────────────────┘
                              ▼
                   Infrastructure Automation
                   ├── Terraform Modules
                   ├── Ansible Playbooks
                   └── Environment Registry
                              │
         ┌────────────────────┼────────────────────┐
         ▼                    ▼                    ▼
       Azure                 AWS                  GCP
         │                    │                    │
         └────────────────────┼────────────────────┘
                              ▼
                     Cloud Native Runtime
                     ├── Kubernetes / AKS / EKS / GKE
                     ├── OpenShift
                     └── Serverless

Cross-Cutting:
┌──────────────────────────────────────────────────────┐
│                SECURITY & GOVERNANCE                  │
│          Policy-as-Code · Approvals · Compliance      │
└──────────────────────────────────────────────────────┘
┌──────────────────────────────────────────────────────┐
│               ENTERPRISE & MULTI-TENANCY              │
│      Org · Tenant · RBAC · Isolation · Audit          │
└──────────────────────────────────────────────────────┘
┌──────────────────────────────────────────────────────┐
│                   COMMERCIALISATION                   │
│     Editions · Entitlements · Metering · Billing      │
└──────────────────────────────────────────────────────┘
┌──────────────────────────────────────────────────────┐
│                   OBSERVABILITY                       │
│        Metrics · Logs · Traces · SLOs                 │
└──────────────────────────────────────────────────────┘
```

## Component Descriptions

### Platform Control Plane

The Control Plane is the operational core. All platform interactions (from the Developer Portal, from CI/CD, from AI agents) route through the Control Plane.

Responsibilities:
- Expose authenticated, authorised platform APIs
- Route and orchestrate cross-module workflows
- Enforce multi-tenancy and RBAC at every request
- Emit platform events to the audit stream
- Provide health, readiness, and operational endpoints

### Developer Portal (Backstage)

Backstage is the developer-facing surface of TRS Platform. It provides a Software Catalog, self-service scaffolding via Software Templates, and TechDocs.

The Developer Portal communicates with the Platform Control Plane via REST APIs and webhooks.

### Template Engine

The Template Engine manages the authoring, versioning, and execution of Backstage Software Templates. It is the mechanism by which Golden Paths are made available to developers as self-service actions.

### Golden Paths

Golden Paths are pre-built, opinionated delivery paths composed from templates, infrastructure modules, CI/CD pipelines, and security controls. They are the primary product delivery mechanism.

See [golden-path-architecture.md](golden-path-architecture.md) for detailed design.

### Infrastructure Automation

Terraform and Ansible automation that provisions and configures cloud infrastructure. Infrastructure modules are parameterised, versioned, and reusable across Golden Paths.

### CI/CD

GitHub Actions and Azure DevOps pipeline templates that implement build, test, security scan, and deploy automation. CI/CD pipelines are Golden-Path-aware and include embedded DevSecOps gates.

### DevSecOps

Security tooling embedded in every Golden Path:
- SAST via Semgrep / SonarQube
- SCA via OWASP Dependency Check / Snyk
- Container scanning via Trivy
- IaC scanning via Checkov / tfsec
- SBOM generation and signing

### Security & Governance

OPA/Rego-based policy engine that enforces platform-wide security and compliance policies. Includes approval workflows, exception management, and compliance reporting.

### Observability

Centralised observability stack: metrics (Prometheus/Azure Monitor), logs (Fluent Bit/Log Analytics), traces (OpenTelemetry), and SLO management.

### AI Platform Engineer

AI agents that operate throughout the delivery lifecycle. See [ai-platform-engineer.md](ai-platform-engineer.md).

### Enterprise & Multi-Tenancy

Multi-tenant organisational hierarchy with full isolation at network, data, and compute layers. See [multi-tenancy.md](multi-tenancy.md).

### Commercialisation

Product edition, entitlement, metering, and billing subsystem.

### Cloud Native & Runtime

Abstractions over Kubernetes, OpenShift, and serverless runtimes, enabling Golden Paths to target multiple runtime environments without changing developer workflows.

## Technology Choices

| Concern | Technology |
|---------|-----------|
| Developer Portal | Backstage |
| Policy Engine | OPA / Rego |
| Infrastructure as Code | Terraform |
| Configuration Management | Ansible |
| Container Orchestration | Kubernetes / OpenShift |
| CI/CD | GitHub Actions / Azure DevOps |
| Observability | OpenTelemetry, Prometheus, Grafana |
| AI | LLM-backed agents (model TBD via ADR) |
| API | REST + gRPC + CloudEvents |

Key technology decisions are recorded as Architecture Decision Records in `docs/adr/`.
