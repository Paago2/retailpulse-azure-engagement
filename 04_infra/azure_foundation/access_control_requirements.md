# Access Control Requirements

## Project

RetailPulse Azure Data Engagement Platform

## Purpose

This document defines the initial access control requirements for the RetailPulse Azure data platform.

The goal is to support least-privilege access, separation of duties, secure data handling, and controlled delivery.

---

## Access Control Principles

1. Grant only the access needed to perform the role.
2. Use groups instead of assigning permissions directly to individuals where possible.
3. Separate development, test, and production access.
4. Avoid giving broad owner permissions to engineers by default.
5. Use managed identities for services and pipelines.
6. Store secrets in Key Vault, not in code or local files.
7. Review access periodically.
8. Keep production access more restricted than development access.

---

## Proposed Role Groups

| Group | Purpose |
|---|---|
| retailpulse-engagement-leads | Roadmap, delivery, stakeholder reporting, backlog oversight |
| retailpulse-cloud-engineers | Azure resource setup, networking, platform configuration |
| retailpulse-data-engineers | Pipelines, ingestion, transformation, data validation |
| retailpulse-bi-developers | Semantic model, Power BI dashboards, report testing |
| retailpulse-governance-security | RBAC, Key Vault, data quality, lineage, access approvals |
| retailpulse-analysts-readonly | Read-only access to curated data or reports |
| retailpulse-support-ops | Monitoring, incident review, operational support |

---

## Access Matrix

| Role Group | Dev | Test | Prod |
|---|---|---|---|
| Engagement Leads | Reader / Contributor to Boards | Reader | Reader |
| Cloud Engineers | Contributor | Contributor with approval | Limited Contributor / controlled change |
| Data Engineers | Contributor to data resources | Contributor with approval | Limited write through pipeline identity |
| BI Developers | Read curated data, create reports | Validate reports | Publish through approved process |
| Governance/Security | Security admin / reviewer | Security reviewer | Security approver |
| Analysts Readonly | Read curated data | Read curated data | Read approved reports only |
| Support/Ops | Monitor and read logs | Monitor and read logs | Monitor and incident access |

---

## Data Layer Access Strategy

| Data Layer | Access Approach |
|---|---|
| Bronze | Restricted to data engineering and platform team |
| Silver | Data engineering, BI developers, governed analysts |
| Gold | BI developers, analysts, business users through approved semantic model |
| Quarantine | Data engineering and governance only |
| Metadata | Data engineering, governance, and platform team |

---

## Azure DevOps Access Strategy

| Azure DevOps Area | Access Approach |
|---|---|
| Boards | Most project team members can view and update assigned work |
| Repos | Developers have repo access based on role |
| Pull Requests | Reviewers and leads approve changes |
| Pipelines | Restricted to DevOps/Cloud engineers and leads |
| Service Connections | Highly restricted |
| Project Settings | Limited to administrators and leads |

---

## Separation of Duties

| Activity | Should Perform | Should Approve |
|---|---|---|
| Create pipeline code | Data Engineer | Tech Lead |
| Modify infrastructure code | Cloud Engineer | Tech Lead / Security |
| Change access rules | Security/Governance Lead | Security Sponsor |
| Publish Power BI report | BI Developer | BI Lead / Business Owner |
| Deploy to production | DevOps/Cloud Engineer | Tech Lead / Engagement Lead |
| Approve KPI definitions | BI Lead / Business Analyst | Business Owner |

---

## Production Access Rules

Production access should be more restricted than development.

Recommended controls:

- No direct manual edits unless approved
- Deploy through pipeline where possible
- Use pull request approvals
- Use environment approvals
- Log changes
- Review access periodically
- Use named accounts and managed identities
- Avoid shared credentials

---

## Leadership Interpretation

Access control is part of delivery governance.

A lead must make sure team members can do their jobs without giving unnecessary access to sensitive systems, secrets, production resources, or business data.