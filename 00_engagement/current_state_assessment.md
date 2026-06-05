# Current-State Assessment

## Data Sources

Northwind Retail Group currently has the following source systems:

| Source System | Data Type | Current Issue |
|---|---|---|
| E-commerce Platform | Online orders, payments, customer activity | Data exported manually; no real-time integration |
| Point-of-Sale System | Store transactions | Delayed batch extracts |
| Inventory System | Product stock levels | Inconsistent product IDs across stores |
| Delivery System | Shipment and fulfillment events | No centralized operational visibility |
| CRM System | Customer profiles and segments | Data quality issues and duplicate customer records |
| Marketing Platform | Campaign data | Not connected to sales performance reporting |

## Reporting Current State

- Reports are created manually from spreadsheets and extracts.
- Different teams calculate KPIs differently.
- There is no governed semantic model.
- Power BI reports exist, but data refreshes are inconsistent.
- Executives lack a single trusted dashboard.

## Architecture Current State

- No centralized data lake.
- No formal Bronze/Silver/Gold data structure.
- Limited orchestration and monitoring.
- No real-time streaming pipeline.
- Data quality checks are mostly manual.
- Governance and lineage are not clearly documented.

## Delivery Current State

- Work is handled reactively.
- There is no unified backlog for data initiatives.
- Stakeholder requests are tracked through email and meetings.
- Risks, blockers, and dependencies are not consistently visible.