# Frontend Skill

## Purpose
Guide developer-facing experiences in the portal, self-service forms, docs surfaces, and golden-path UX.

## When to use
Use for work items involving Backstage plugins, template forms, onboarding flows, status views, or documentation-linked UX.

## Inputs expected from a Plane work item
- User persona and workflow to support
- Required form fields, validation, and module ownership
- Tenant-aware visibility rules and approval touchpoints
- Accessibility, usability, and documentation expectations

## Output contract
- UI behavior definition or implementation changes
- Field validation and user-flow updates
- Notes on backend dependencies, audit surfaces, and docs impact

## Guardrails
- Keep terminology aligned with TRS Platform module names
- Do not expose secrets, provider credentials, or hidden tenant data
- Prefer clear self-service flows over bespoke one-off experiences

## Definition of done
- [ ] User journey is explicit
- [ ] Inputs and validation rules are documented
- [ ] Tenant-aware visibility is respected
- [ ] Backend and docs dependencies are identified
- [ ] UX supports the golden path without bypassing governance
