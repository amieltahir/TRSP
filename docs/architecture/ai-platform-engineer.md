# TRS Platform — AI Platform Engineer

## Overview

The AI Platform Engineer is Module 11 of TRS Platform. It embeds AI agents throughout the software delivery lifecycle, providing intelligent assistance at every stage — from code generation to security remediation to operational response.

## Core Capabilities

| Capability | Description |
|-----------|-------------|
| **Code Generation** | Generate application scaffolding, boilerplate, and implementation from specifications |
| **Automated Code Review** | Analyse code for quality, security, and standards compliance |
| **Security Remediation** | Identify and suggest fixes for security findings from DevSecOps scans |
| **Infrastructure Generation** | Generate Terraform and Ansible from natural-language or structured specifications |
| **Pipeline Generation** | Generate CI/CD pipeline configurations for new services |
| **Documentation Generation** | Generate TechDocs, README files, API documentation |
| **AI-Assisted Debugging** | Analyse logs, traces, and error patterns to suggest root-cause fixes |
| **Incident Response** | Assist on-call engineers with incident triage and remediation steps |

## Agent Architecture

AI Platform Engineer agents operate as autonomous or semi-autonomous agents:

```
                    PLATFORM CONTROL PLANE
                             │
                    AI Orchestration Layer
                             │
         ┌───────────────────┼───────────────────┐
         ▼                   ▼                   ▼
   Generation Agent    Review Agent      Remediation Agent
         │                   │                   │
         ▼                   ▼                   ▼
    LLM Backend         LLM Backend         LLM Backend
         │                   │                   │
         └───────────────────┼───────────────────┘
                             │
                    Tool Integrations
                    ├── GitHub API
                    ├── Backstage API
                    ├── Terraform
                    ├── CI/CD pipelines
                    ├── Security scanners
                    └── Observability stack
```

## Context Model

Agents are context-aware. Before acting, every agent reads:

1. `CLAUDE.md` — engineering standards and agent instructions (repository root)
2. `docs/product/roadmap.md` — product architecture and module definitions
3. `docs/architecture/` — system architecture and component design
4. `docs/adr/` — architecture decisions
5. Assigned Plane work item — the specific task or story
6. Repository code — existing implementation

This ensures agents operate within the product architecture, not against it.

## Engineering Agent Standards (Claude)

When Claude Code or another AI coding agent operates on this repository, it must:

1. Read `CLAUDE.md` before making any code changes
2. Read the relevant architecture documents for the capability being implemented
3. Implement only what is specified in the assigned Plane work item
4. Follow the engineering standards in `docs/engineering/`
5. Emit an ADR for any significant architecture decision
6. Run tests and security scans before committing

## AI Workflow Integration in Golden Paths

Every Golden Path includes an AI Workflow integration point. This provides:

- Automated code review on every pull request
- Security finding analysis and remediation suggestions
- Dependency upgrade recommendations
- Test coverage analysis

## Governance

AI agents operate within the Security & Governance framework:

- All agent actions are audit-logged with full context
- Agents cannot bypass RBAC or tenant isolation
- Agent-generated code must pass the same DevSecOps gates as human-written code
- Sensitive operations (production deployments, credential management) require human approval
- AI context (prompts, completions) is stored per-tenant and subject to data retention policies

## LLM Selection

The choice of LLM backend for each agent type is governed by ADR. Criteria include:

- Capability for the specific task type
- Data residency requirements
- Cost per token
- Latency requirements
- Security and privacy classification of input data
