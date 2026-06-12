# Cost-Risk Services

## Project

RetailPulse Azure Data Engagement Platform

## Purpose

This document identifies Azure services that may create cost risk during the RetailPulse Azure data modernization engagement.

The goal is to help the team understand which services require careful sizing, monitoring, shutdown, or approval.

---

## Cost-Risk Categories

| Risk Level | Meaning |
|---|---|
| Low | Usually low cost for small development usage |
| Medium | Cost depends on usage, run frequency, retention, or data volume |
| High | Can become expensive quickly if compute or premium resources are left running |

---

## Azure Service Cost-Risk Matrix

| Service | Risk Level | Cost Driver | Mitigation |
|---|---|---|---|
| Azure DevOps Boards | Low | Users/features beyond free tier | Keep small team; avoid paid Test Plans unless needed |
| Azure Storage / ADLS Gen2 | Low to Medium | Storage volume, transactions, redundancy | Use small datasets; choose appropriate redundancy; clean up test files |
| Azure Data Factory | Low to Medium | Pipeline activity runs, data movement, integration runtime | Limit test runs; avoid unnecessary scheduled triggers |
| Azure Event Hubs | Low to Medium | Tier, throughput units, retention, event volume | Use small dev tier; limit event producer volume |
| Azure Databricks | High | Running clusters, DBUs, VM cost | Use small clusters; auto-terminate; shut down after use |
| Azure Synapse Dedicated SQL Pool | High | Dedicated compute running | Avoid dedicated pools unless justified; pause when not in use |
| Azure Synapse Serverless | Medium | Data scanned per query | Use small files and partitioning; avoid repeated broad scans |
| Log Analytics | Medium | Ingested log volume and retention | Limit verbose logging; set retention appropriately |
| Azure Key Vault | Low | Operations and key usage | Usually low, but avoid excessive automated calls |
| Azure Monitor | Medium | Metrics, logs, alerts | Monitor log ingestion volume |
| Power BI | Depends | Licensing and capacity | Use existing license/free capabilities where possible |
| Azure OpenAI | Medium to High | Token usage and deployment configuration | Use only after data foundation and budget controls are ready |
| Azure Machine Learning | Medium to High | Compute clusters and endpoint hosting | Use small compute; shut down clusters; avoid always-on endpoints |

---

## Highest-Risk Services for This Project

For RetailPulse, the highest cost risks are:

1. Azure Databricks clusters left running
2. Synapse dedicated SQL pools left running
3. Excessive Log Analytics ingestion
4. Uncontrolled Event Hubs event volume
5. Always-on ML endpoints
6. Repeated large serverless SQL scans
7. Premium Power BI/Fabric capacity if enabled

---

## Services to Avoid in Early Sprints

Do not use these until needed:

| Service | Reason |
|---|---|
| Synapse Dedicated SQL Pool | Can be expensive if left running |
| Large Databricks clusters | Not needed for small sample data |
| Premium Event Hubs | Not needed for demo event volume |
| Always-on ML endpoints | Not needed until ML use case is implemented |
| Premium Power BI/Fabric capacity | Not needed for early architecture/demo |

---

## Safer Early-Stage Choices

| Need | Safer Starting Point |
|---|---|
| Data lake | ADLS Gen2 with small sample data |
| Batch orchestration | ADF with limited manual test runs |
| Streaming | Event Hubs basic/standard with low event volume |
| Transformation | Local PySpark or small Databricks cluster with auto-termination |
| BI | Power BI Desktop or existing workspace |
| Governance | Documentation-first, then Purview later if needed |

---

## Cost Review Questions

Before deploying a service, ask:

1. Is this service required for the current sprint?
2. Is there a lower-cost alternative for learning/testing?
3. Can it be turned off?
4. Does it have auto-shutdown or pause capability?
5. Who owns the resource?
6. Is the resource tagged?
7. What is the expected daily/monthly cost?
8. What is the cleanup plan?

---

## Leadership Interpretation

Cost-risk awareness is part of technical leadership.

An Engagement & Technical Lead should be able to explain not only what Azure services are needed, but also which ones create financial risk and how the team will control them.