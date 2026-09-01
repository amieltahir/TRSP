# Contributing to TRS Platform

## Source of Truth Policy

### GitHub is the authoritative source for:
- Product vision, architecture, and roadmap
- Technical decisions (Architecture Decision Records)
- Engineering standards
- Golden Path definitions
- Multi-tenancy and commercialisation architecture

### Plane is the authoritative source for:
- Modules, epics, features, stories, tasks
- Sprints/cycles and delivery status
- Assignments, priorities, and progress

**Changes to product architecture or technical direction must be reflected in GitHub first. Implementation work derived from those decisions is then tracked in Plane.**

### Claude Code and other engineering agents must:
1. Read `CLAUDE.md` before making any code changes
2. Read `docs/product/roadmap.md` to understand the product
3. Read the relevant `docs/architecture/` documents
4. Reference the assigned Plane work item for the specific task
5. Follow the engineering standards in `docs/engineering/`

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
│   ├── architecture/
│   │   ├── system-architecture.md
│   │   ├── golden-path-architecture.md
│   │   ├── multi-tenancy.md
│   │   └── ai-platform-engineer.md
│   ├── adr/
│   └── engineering/
└── .claude/
```

## How to Contribute

### Product Documentation

Product documentation changes (vision, roadmap, architecture) are made via pull request and require review from the product/architecture owner.

### Architecture Decision Records

Significant technical decisions must be captured as ADRs in `docs/adr/`. See `docs/adr/README.md` for the template and process.

### Code Changes

All code changes:
1. Must be derived from a Plane work item (story/task)
2. Must include tests
3. Must pass CI/CD and DevSecOps gates
4. Must be reviewed before merging

### Naming Conventions

- Use "TRS Platform" as the product name (not "Aurex")
- Module names must exactly match the 16 modules in `docs/product/roadmap.md`

## Branching Strategy

- `main` — stable, deployable
- `develop` — integration branch (if used)
- Feature branches: `feature/<plane-issue-id>-short-description`
- Fix branches: `fix/<plane-issue-id>-short-description`

## Commit Messages

Use conventional commits:

```
feat(module): short description
fix(module): short description
docs(module): short description
chore: short description
```

Where `module` is the short name of the relevant TRS Platform module (e.g. `golden-paths`, `control-plane`, `developer-portal`).
