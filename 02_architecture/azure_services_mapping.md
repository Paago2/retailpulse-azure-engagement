
---

# Step 3: Fill `azure_services_mapping.md`

```markdown
# Azure Services Mapping

## Purpose

This document maps each platform capability to the Azure service that supports it.

| Capability | Azure Service | Purpose |
|---|---|---|
| Batch orchestration | Azure Data Factory | Schedule and orchestrate batch ingestion pipelines |
| Real-time event ingestion | Azure Event Hubs | Capture streaming order and fulfillment events |
| Data lake storage | ADLS Gen2 | Store Bronze, Silver, and Gold data layers |
| Transformation | Azure Databricks | Clean, standardize, transform, and model data |
| Warehouse serving layer | Azure Synapse or Fabric Warehouse | Serve curated data for analytics if needed |
| Reporting | Power BI | Build dashboards and governed semantic models |
| Governance | Microsoft Purview | Catalog data assets, lineage, and business glossary |
| Secrets management | Azure Key Vault | Store secrets, keys, and connection strings |
| Access control | Azure RBAC and Entra ID | Manage least-privilege access |
| Monitoring | Azure Monitor and Log Analytics | Monitor pipelines, resources, and failures |
| Delivery management | Azure DevOps Boards | Manage epics, features, user stories, tasks, and sprints |
| CI/CD | Azure Pipelines or GitHub Actions | Automate deployment later in the project |

## Notes

Azure DevOps Boards is used for sprint and delivery management.

Azure Pipelines or GitHub Actions would be used later for CI/CD automation.

No paid Azure cloud infrastructure is deployed during Sprint 1.