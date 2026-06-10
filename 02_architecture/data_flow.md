# Data Flow

## Batch Data Flow

```text
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