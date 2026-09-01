# TRS Platform — Golden Path Architecture

## Overview

A Golden Path is a fully opinionated, pre-integrated delivery path that combines:

- **Language** — the application programming language and runtime
- **Cloud** — the target cloud provider
- **Runtime** — the compute and container runtime
- **DevSecOps** — embedded security gates
- **CI/CD** — build and deploy automation
- **Observability** — metrics, logs, and traces
- **AI Workflow** — AI-assisted generation, review, and remediation

Golden Paths are the primary mechanism by which TRS Platform delivers value to developers.

## Composition Model

A Golden Path is composed from reusable, versioned modules:

```
Golden Path
│
├── Template Module       (Template Engine)
│   ├── Repository scaffold
│   ├── Application skeleton
│   └── Configuration files
│
├── Infrastructure Module (Infrastructure Automation)
│   ├── Terraform: cloud resources
│   ├── Terraform: networking
│   └── Terraform: IAM
│
├── Pipeline Module       (CI/CD)
│   ├── Build pipeline
│   ├── Test pipeline
│   └── Deploy pipeline
│
├── Security Module       (DevSecOps)
│   ├── SAST gate
│   ├── SCA gate
│   ├── Container scan gate
│   └── IaC scan gate
│
├── Runtime Module        (Cloud Native & Runtime)
│   ├── Helm chart / Kubernetes manifests
│   └── Runtime configuration
│
├── Observability Module  (Observability)
│   ├── Metrics configuration
│   ├── Log configuration
│   └── Trace configuration
│
└── AI Module             (AI Platform Engineer)
    ├── Code review agent
    ├── Security remediation agent
    └── Documentation agent
```

## Golden Path Lifecycle

```
DESIGN → IMPLEMENT → TEST → PROMOTE → MAINTAIN → DEPRECATE
```

| Stage | Description |
|-------|-------------|
| **Design** | ADR capturing the language/cloud/runtime combination and component choices |
| **Implement** | Build each component module and compose the Golden Path |
| **Test** | Run the Testing & Quality gate: unit, integration, E2E validation |
| **Promote** | Make the path available in the Developer Portal via Backstage |
| **Maintain** | Version, patch, and update; notify consumers of breaking changes |
| **Deprecate** | Mark deprecated; maintain for 2 major versions; remove |

## Path Versioning

Each Golden Path is independently versioned using semantic versioning:

- `MAJOR` — breaking changes (e.g. Terraform module API change)
- `MINOR` — new capabilities added (e.g. new observability integration)
- `PATCH` — bug fixes, security patches

## Developer Experience

From a developer's perspective, a Golden Path is a single Backstage Software Template action:

1. Open Developer Portal
2. Choose "New Service" → select Golden Path (e.g. "Java on Azure Kubernetes")
3. Provide service name, team, environment targets
4. Platform creates: repository, CI/CD pipeline, infrastructure, Backstage catalog entry
5. Developer clones repository and starts writing business logic

The platform takes care of everything else.

## Extending a Golden Path

Teams may extend a Golden Path to add custom modules, but must not modify the platform-owned modules. Extension points are:

- Custom Terraform modules (added to `infrastructure/custom/`)
- Custom pipeline steps (added to designated extension points in the pipeline)
- Custom Backstage plugins (registered via the Developer Portal)

Extensions are subject to Security & Governance policy review.

## Language × Cloud × Runtime Matrix

See [golden-path-roadmap.md](../product/golden-path-roadmap.md) for the full matrix.
