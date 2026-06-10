# Data Flow

## Batch Data Flow


Customer/Product/Store/Inventory Sources
        |
        v
Azure Data Factory
        |
        v
ADLS Gen2 Bronze
        |
        v
Databricks Transformation
        |
        v
ADLS Gen2 Silver
        |
        v
Gold Reporting Tables
        |
        v
Power BI Dashboards


## Streaming Data Flow

Order and Fulfillment Events
        |
        v
Azure Event Hubs
        |
        v
Stream Processing
        |
        v
ADLS Gen2 Bronze
        |
        v
Databricks Transformation
        |
        v
Silver Operational Events
        |
        v
Gold Operational Metrics
        |
        v
Power BI Operational Dashboard

## Governance Flow

Data Assets
    |
    v
Catalog and Glossary
    |
    v
Data Quality Rules
    |
    v
Access Control and RLS
    |
    v
Trusted Reporting and Auditability

## Delivery Flow

Client Discovery
    |
    v
Epics
    |
    v
Features
    |
    v
User Stories
    |
    v
Tasks
    |
    v
Sprint Execution
    |
    v
Review and Handoff