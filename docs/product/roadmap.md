# TRS Platform — Product Roadmap

## 16 Core Product Modules

TRS Platform is organised into 16 core product modules. These modules represent major product capability domains and form the stable product taxonomy.

| # | Module | Purpose |
|---|--------|---------|
| 01 | **Product & Architecture** | Product vision, architecture, ADRs, technical standards |
| 02 | **Platform Control Plane** | Core platform APIs, orchestration, platform services |
| 03 | **Developer Portal** | Backstage integration, catalog, UX, self-service |
| 04 | **Template Engine** | Reusable templates, scaffolding, template lifecycle |
| 05 | **Golden Paths** | Golden-path framework and composition |
| 06 | **Infrastructure Automation** | Terraform, Ansible, cloud provisioning, environments |
| 07 | **CI/CD** | Pipeline automation, GitHub/ADO, build/deploy |
| 08 | **DevSecOps** | SAST, SCA, containers, IaC security, supply chain |
| 09 | **Security & Governance** | Policy-as-code, approvals, exceptions, compliance |
| 10 | **Observability** | Metrics, logs, traces, SLOs, monitoring |
| 11 | **AI Platform Engineer** | AI workflow orchestration for generation, review, remediation, and platform assistance |
| 12 | **Enterprise & Multi-Tenancy** | Organisations, tenants, isolation, RBAC, enterprise controls |
| 13 | **Commercialisation** | SaaS, licensing, plans, metering, billing, marketplace |
| 14 | **Documentation** | TechDocs, platform documentation, runbooks, guides |
| 15 | **Testing & Quality** | Unit, integration, E2E, platform validation, evaluations |
| 16 | **Cloud Native & Runtime** | Kubernetes, OpenShift, containers, serverless, runtime abstractions |

Module 11 follows a bring-your-own-AI (BYO-AI) model. Customers connect their own AI providers, models, subscriptions, and gateways; TRS Platform supplies workflow orchestration, guardrails, auditability, and platform integration rather than reselling model tokens.

## Delivery Waves

Delivery is organised around Golden Path families: Language × Cloud × Runtime.

### Wave 1 — Java on Azure Kubernetes
```
Java
 └── Azure
      └── Kubernetes
           ├── DevSecOps
           └── AI Workflow
```

### Wave 2 — Python on Azure Kubernetes
```
Python
 └── Azure
      └── Kubernetes
           ├── DevSecOps
           └── AI Workflow
```

### Wave 3 — .NET on Azure Kubernetes
```
.NET
 └── Azure
      └── Kubernetes
           ├── DevSecOps
           └── AI Workflow
```

### Wave 4 — Azure Functions (Serverless)
```
Azure Functions
 └── Azure
      └── Serverless
           ├── DevSecOps
           └── AI Workflow
```

### Wave 5+ — AWS and GCP
Apply the same repeatable factory pattern across AWS and GCP, reusing the same governance, observability, and customer-managed AI connectivity model.

## Sprint 0 — Architecture & Foundation

Sprint 0 is the architecture and foundation sprint. Its purpose is to establish:

- Repository structure and source-of-truth governance
- Product documentation baseline
- Architecture Decision Records (ADRs) for key platform decisions
- Plane module structure aligned to the 16 modules above
- Initial Epic hierarchy in Plane
- CLAUDE.md and agent engineering standards

Sprint 0 does **not** deliver functional platform code. It delivers the foundation that makes every subsequent sprint safe, deterministic, and well-directed.

## Plane Module Naming Convention

Plane modules must exactly mirror the 16 product modules listed above:

```
01 Product & Architecture
02 Platform Control Plane
03 Developer Portal
04 Template Engine
05 Golden Paths
06 Infrastructure Automation
07 CI/CD
08 DevSecOps
09 Security & Governance
10 Observability
11 AI Platform Engineer
12 Enterprise & Multi-Tenancy
13 Commercialisation
14 Documentation
15 Testing & Quality
16 Cloud Native & Runtime
```

## Workflow and Onboarding Concepts

**Core Workflow** and **Onboarding Flow** are not modules. They are implementation and workflow concepts that belong as Epics inside the appropriate modules:

```
Developer Portal
    └── Epic: Developer Onboarding
         ├── Feature: Repository Creation
         ├── Feature: Backstage Registration
         ├── Feature: Environment Selection
         └── Feature: First Deployment

Platform Control Plane
    └── Epic: Core Workflow Engine
         ├── Feature: Workflow Definition
         ├── Feature: Workflow Execution
         ├── Feature: Workflow State
         └── Feature: Workflow Audit
```
