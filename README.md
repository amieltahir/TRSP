# TRS Platform

TRS Platform is an Internal Developer Platform (IDP) that accelerates software delivery through golden paths, AI-assisted engineering, and a fully automated DevSecOps pipeline.

## Repository Structure

```
TRS-Platform/
├── README.md
├── CONTRIBUTING.md
├── CLAUDE.md
├── docs/
│   ├── product/
│   │   ├── vision.md
│   │   ├── roadmap.md
│   │   ├── product-capabilities.md
│   │   ├── golden-path-roadmap.md
│   │   └── product-map.md
│   │
│   ├── architecture/
│   │   ├── system-architecture.md
│   │   ├── golden-path-architecture.md
│   │   ├── multi-tenancy.md
│   │   └── ai-platform-engineer.md
│   │
│   ├── adr/
│   └── engineering/
│
└── .claude/
```

## Source of Truth

| Source | Purpose |
|--------|---------|
| **GitHub** | Product vision, architecture, technical decisions, roadmap definitions, engineering standards |
| **Plane** | Modules, epics, features, stories, tasks, cycles, assignments, priorities, delivery status |
| **Claude Code / Agents** | Implementation, guided by repository documentation and Plane work items |
| **Git** | Immutable record of what actually changed |

## Quick Links

- [Product Vision](docs/product/vision.md)
- [Product Roadmap](docs/product/roadmap.md)
- [System Architecture](docs/architecture/system-architecture.md)
- [Golden Path Architecture](docs/architecture/golden-path-architecture.md)
- [Multi-Tenancy](docs/architecture/multi-tenancy.md)
- [AI Platform Engineer](docs/architecture/ai-platform-engineer.md)
- [Contributing](CONTRIBUTING.md)
