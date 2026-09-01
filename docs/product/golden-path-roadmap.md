# TRS Platform — Golden Path Roadmap

## Overview

Golden Paths are not modules. They are delivery families that combine three dimensions:

```
                    GOLDEN PATHS
                         │
          ┌──────────────┼──────────────┐
          │              │              │
       Language         Cloud         Runtime
          │              │              │
     Java/Python      Azure/AWS/GCP   K8s/OpenShift
     .NET/Node.js     │              Serverless
     Go               │              Containers
```

Each Golden Path is a fully opinionated combination of a language, a cloud provider, and a runtime target, with embedded CI/CD, DevSecOps, observability, and AI workflow.

## Golden Path Matrix

### Language Families

| Language | Status |
|----------|--------|
| Java | Wave 1 |
| Python | Wave 2 |
| .NET | Wave 3 |
| Node.js | Future |
| Go | Future |

### Cloud Targets

| Cloud | Status |
|-------|--------|
| Azure | Wave 1–4 |
| AWS | Wave 5 |
| GCP | Wave 6 |

### Runtime Targets

| Runtime | Status |
|---------|--------|
| Kubernetes | Wave 1–3 |
| Serverless (Azure Functions) | Wave 4 |
| OpenShift | Future |
| Containers (non-K8s) | Future |

## Full Path Matrix

```
Golden Paths
│
├── Java
│   ├── Azure + Kubernetes      ← Wave 1
│   ├── AWS + Kubernetes        ← Wave 5
│   └── GCP + Kubernetes        ← Wave 6
│
├── Python
│   ├── Azure + Kubernetes      ← Wave 2
│   ├── AWS + Kubernetes        ← Wave 5
│   └── GCP + Kubernetes        ← Wave 6
│
├── .NET
│   ├── Azure + Kubernetes      ← Wave 3
│   ├── AWS + Kubernetes        ← Wave 5
│   └── GCP + Kubernetes        ← Wave 6
│
└── Azure Functions
    └── Azure + Serverless      ← Wave 4
```

## What Each Golden Path Includes

Every Golden Path delivers the following capabilities as a fully integrated package:

| Capability | Component |
|-----------|-----------|
| Repository scaffold | Template Engine + Backstage |
| Build pipeline | CI/CD module |
| Security scanning | DevSecOps module |
| Infrastructure | Infrastructure Automation module |
| Deployment | Cloud Native & Runtime module |
| Observability | Observability module |
| Documentation | Documentation module |
| AI workflow | AI Platform Engineer module |

## Wave 1 Detail: Java on Azure Kubernetes

```
Java
 └── Azure
      └── Kubernetes
           ├── Maven/Gradle build pipeline
           ├── SAST (SonarQube / Semgrep)
           ├── SCA (OWASP Dependency Check)
           ├── Container scanning (Trivy)
           ├── Terraform: AKS cluster + networking
           ├── Helm chart deployment
           ├── Azure Monitor integration
           └── AI code review and remediation
```

### Wave 1 Epic Breakdown (Plane)

```
Golden Paths
└── Epic: Java on Azure Kubernetes
     ├── Feature: Java project template (Backstage)
     ├── Feature: Azure infrastructure (Terraform)
     ├── Feature: Kubernetes deployment (Helm)
     ├── Feature: CI/CD pipeline (GitHub Actions)
     ├── Feature: Security controls (DevSecOps)
     ├── Feature: Observability (Azure Monitor)
     └── Feature: AI workflow integration
```

## Governance

- New Golden Paths must be proposed via an ADR in `docs/adr/`
- Golden Paths are versioned and must pass the Testing & Quality gate before promotion
- Deprecated paths must remain available for 2 major versions
- The Golden Path composition model is defined in [golden-path-architecture.md](../architecture/golden-path-architecture.md)
