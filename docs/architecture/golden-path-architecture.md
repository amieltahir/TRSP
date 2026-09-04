# TRS Platform — Golden Path Architecture

## Overview

A Golden Path is a composed delivery baseline that combines templates, infrastructure automation, CI/CD, DevSecOps, runtime configuration, observability, and optional AI workflow integration into a repeatable developer experience.

## Golden Path Composition

Each Golden Path is built from the following product modules:

```text
Golden Path
├── Template Module       (Template Engine)
│   ├── Service template
│   ├── Repository scaffold
│   └── Backstage parameters
│
├── Infrastructure Module (Infrastructure Automation)
│   ├── Terraform modules
│   ├── Cloud resources
│   └── Environment bootstrap
│
├── Pipeline Module       (CI/CD)
│   ├── Build pipeline
│   ├── Test pipeline
│   └── Deploy pipeline
│
├── DevSecOps Module      (DevSecOps)
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
└── AI Workflow Module    (AI Platform Engineer)
    ├── Review workflow
    ├── Security remediation workflow
    └── Documentation workflow
```

## Golden Path Lifecycle

```text
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
5. Platform applies embedded security, runtime, observability, and optional AI workflow standards
