# Target-State Vision

## Vision Statement

Northwind Retail Group will modernize its data platform on Azure to provide trusted, governed, and timely analytics for executive decision-making, operational monitoring, and future AI/ML use cases.

## Target Architecture

The target platform will include:

1. Azure Data Factory for batch ingestion and orchestration
2. Azure Event Hubs for real-time order and fulfillment events
3. Azure Data Lake Storage Gen2 for Bronze, Silver, and Gold data layers
4. Azure Databricks or Azure Synapse for transformation and analytics processing
5. Power BI for executive, operational, inventory, and data quality dashboards
6. Microsoft Purview for cataloging, lineage, and governance
7. Azure Key Vault and RBAC for security and secrets management
8. Azure DevOps Boards for roadmap, sprint, backlog, risk, and delivery tracking

## Data Layering Strategy

| Layer | Purpose |
|---|---|
| Bronze | Raw ingested data from source systems and event streams |
| Silver | Cleaned, validated, standardized, and joined data |
| Gold | Business-ready analytics tables and KPI-focused models |

## Target Business Outcomes

- Trusted executive reporting
- Near-real-time order and fulfillment visibility
- Reduced manual reporting effort
- Standardized KPI definitions
- Improved data quality monitoring
- Governed access to sensitive data
- Scalable foundation for AI/ML and LLM use cases