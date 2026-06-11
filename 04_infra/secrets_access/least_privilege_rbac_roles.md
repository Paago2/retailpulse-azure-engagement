# Least-Privilege RBAC Roles

## Project

RetailPulse Azure Data Engagement Platform

## Purpose

This document defines the least-privilege RBAC approach for the RetailPulse Azure data platform.

The goal is to ensure that each role receives only the access required to complete assigned work.

---

## Least-Privilege Principle

Least privilege means:

> Give users and services the minimum permissions required to perform their responsibilities, for the shortest reasonable time, and only in the appropriate environment.

---

## Role-Based Access Model

| Role Group | Primary Need | Recommended Access |
|---|---|---|
| Engagement Leads | Track delivery, risks, stakeholders | Azure Boards access; Azure Reader if needed |
| Cloud Engineers | Create and configure Azure resources | Contributor in dev; restricted contributor in test/prod |
| Data Engineers | Build pipelines, validate data | Contributor to data services in dev; pipeline-based access in prod |
| Streaming Engineers | Configure Event Hubs and streaming jobs | Contributor to streaming resources in dev/test |
| BI Developers | Build semantic models and dashboards | Read curated data; Power BI workspace access |
| Governance/Security Leads | Review access, data quality, secrets | Security/admin review permissions |
| DevOps Engineers | Configure CI/CD and deployment workflows | Pipeline permissions and deployment approval access |
| Analysts | Consume reports and curated data | Read-only access to Gold data or Power BI reports |
| Support/Ops | Monitor and troubleshoot | Reader/Monitoring Reader; limited incident access |

---

## Azure Role Examples

| Azure Role | Use Case |
|---|---|
| Reader | View resources but cannot modify |
| Contributor | Create and manage resources, but not grant access |
| Owner | Full control including access assignment; restrict heavily |
| Storage Blob Data Reader | Read data in storage containers |
| Storage Blob Data Contributor | Read/write data in storage containers |
| Key Vault Secrets User | Read secrets when authorized |
| Key Vault Administrator | Manage Key Vault; restrict heavily |
| Monitoring Reader | View monitoring data |
| Log Analytics Reader | View logs |
| Event Hubs Data Sender | Send events to Event Hubs |
| Event Hubs Data Receiver | Receive events from Event Hubs |

---

## Environment-Based Access

| Environment | Access Strategy |
|---|---|
| Dev | More flexible access for building and testing |
| Test | Controlled access for validation |
| Prod | Highly restricted access; deployment through approved process |

---

## Service Identity Strategy

Services should use managed identities where possible.

Examples:

| Service | Identity Pattern |
|---|---|
| Azure Data Factory | System-assigned managed identity |
| Azure Databricks | Managed identity or service principal pattern |
| Azure Functions / Apps | Managed identity |
| Azure Pipelines | Federated identity or service connection |
| Terraform | OIDC/federated identity where possible |

---

## Separation of Duties

| Activity | Implemented By | Approved By |
|---|---|---|
| Create infrastructure | Cloud Engineer | Tech Lead |
| Modify RBAC | Security/Governance Lead | Security Sponsor |
| Build data pipeline | Data Engineer | Tech Lead |
| Publish dashboard | BI Developer | BI Lead / Business Owner |
| Deploy to production | DevOps/Cloud Engineer | Tech Lead / Engagement Lead |
| Access production secrets | Approved service identity | Security/Governance Lead |

---

## Example Access Boundary

A BI Developer may need access to:

- Gold curated tables
- Power BI workspace
- Semantic model files
- Dashboard requirements

A BI Developer should not need access to:

- Production Key Vault secrets
- Raw customer data in Bronze unless approved
- Infrastructure service connections
- Event Hub connection strings
- Terraform backend credentials

---

## Azure DevOps Permission Model

| Area | Recommended Access |
|---|---|
| Boards | Most project contributors can view and update assigned work |
| Repos | Developers can contribute through branches and pull requests |
| Main branch | Protected; requires pull request approval |
| Pipelines | Restricted to DevOps/Cloud engineers and leads |
| Service connections | Highly restricted |
| Project settings | Admins and technical leads only |

---

## Leadership Interpretation

Least privilege helps balance delivery speed with security.

A lead should make sure team members have enough access to complete their assigned work, but not broad access that creates unnecessary risk.