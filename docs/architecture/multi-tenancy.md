# TRS Platform — Multi-Tenancy Architecture

## Overview

Multi-tenancy is a first-class architecture concern in TRS Platform. It is not bolted on after the fact. Every resource in the platform carries tenant context, and authorisation is enforced at the platform level.

## Organisational Hierarchy

```
TRS Platform
 │
 ├── Organisation
 │      │
 │      ├── Tenant
 │      │     │
 │      │     ├── Projects
 │      │     ├── Teams
 │      │     ├── Environments
 │      │     ├── Credentials
 │      │     ├── Policies
 │      │     └── Golden Paths
 │      │
 │      └── Users
 │
 └── Platform Administration
```

### Definitions

| Level | Description |
|-------|-------------|
| **Organisation** | The top-level enterprise customer entity. An Organisation has one or more Tenants. |
| **Tenant** | An isolated unit within an Organisation. Typically maps to a business unit, product group, or team. |
| **Project** | A logical grouping of services and resources within a Tenant. |
| **Team** | A group of Users within a Tenant, assigned to one or more Projects. |
| **Environment** | A deployment target (dev, test, staging, production) scoped to a Tenant. |

## Resource Tenancy

Every important resource carries tenant context:

```json
{
  "resource_id": "...",
  "resource_type": "service",
  "organisation_id": "org_...",
  "tenant_id": "ten_...",
  "project_id": "proj_...",
  "created_by": "user_...",
  "created_at": "..."
}
```

Resources that carry tenant context include:

- Services (catalog entries)
- Repositories
- Environments
- Cloud credentials
- Infrastructure state
- Secrets references
- Policies
- Golden Paths
- AI context and memory
- Deployment records
- Audit events
- Customer data

## Isolation Boundaries

| Layer | Isolation Mechanism |
|-------|-------------------|
| **API** | Every request authenticated + authorised; tenant context extracted from JWT claims |
| **Data** | Tenant ID included in all queries; database-level row-security policies |
| **Storage** | Tenant-prefixed object storage paths |
| **Networking** | Tenant-namespaced Kubernetes namespaces; network policies enforcing isolation |
| **Secrets** | Tenant-scoped vault paths |
| **Audit** | Audit log events tagged with tenant and organisation IDs |

## RBAC Model

Roles are scoped per tenant:

| Role | Scope | Permissions |
|------|-------|-------------|
| **Platform Admin** | Platform | Full access to all organisations and tenants |
| **Organisation Admin** | Organisation | Manage tenants, users, billing |
| **Tenant Admin** | Tenant | Manage projects, teams, environments, policies |
| **Developer** | Project | Create services, deploy, view logs |
| **Viewer** | Project | Read-only access |

Roles are enforced at the Platform Control Plane layer. No service may bypass RBAC.

## Intersection with Commercialisation

Tenant context is the anchor for all commercialisation decisions:

- Feature entitlements are evaluated per Tenant (via Subscription Plan)
- Usage metering is aggregated per Tenant
- Quotas are enforced per Tenant
- Billing is calculated per Organisation

## Platform Administration

Platform Administration is a separate, elevated context for TRS Platform operators. It is not a Tenant. Platform Admins can:

- Create and manage Organisations
- Configure platform-wide policies
- Monitor platform health across all Tenants
- Access audit logs across all Organisations

Platform Administration access is strictly controlled and audited.
