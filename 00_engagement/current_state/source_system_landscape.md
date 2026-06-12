# Source System Landscape

## Project

RetailPulse Azure Data Engagement Platform

## Simulated Client

Northwind Retail Group

## Purpose

This document reviews the current source system landscape for Northwind Retail Group.

The goal is to understand which systems produce business data, what data domains they support, how data is currently extracted, and what issues affect analytics delivery.

---

## Current Source Systems

| Source System | Business Domain | Data Produced | Current Integration Pattern | Current Issues |
|---|---|---|---|---|
| E-commerce Platform | Online sales | Online orders, carts, payments, customer activity | Manual exports and scheduled CSV extracts | Delayed reporting, no real-time order visibility |
| Point-of-Sale System | Store sales | In-store transactions, store receipts, returns | Daily batch extract | Store data arrives late and sometimes has inconsistent product IDs |
| Inventory Management System | Inventory | Stock levels, reorder points, warehouse/store inventory | Spreadsheet exports and database extracts | Product identifiers are inconsistent across systems |
| CRM System | Customer | Customer profiles, segments, contact preferences | Periodic export | Duplicate customer records and incomplete profiles |
| Delivery/Fulfillment System | Operations | Shipment status, delivery milestones, fulfillment delays | Manual reports and API availability not yet standardized | No centralized fulfillment visibility |
| Marketing Platform | Marketing | Campaigns, impressions, clicks, promotions | CSV export | Campaign data not linked consistently to sales outcomes |
| Finance System | Finance | Revenue reconciliation, refunds, financial adjustments | Month-end export | Finance metrics do not always match operational sales reports |

---

## Data Domain Summary

| Data Domain | Main Source | Business Use |
|---|---|---|
| Customers | CRM, E-commerce | Segmentation, retention, sales analysis |
| Products | Inventory System, POS | Product sales, inventory planning |
| Stores | POS, Operations | Store performance reporting |
| Orders | E-commerce, POS | Revenue, order volume, fulfillment analysis |
| Payments | E-commerce, Finance | Payment success, reconciliation |
| Inventory | Inventory System | Stock monitoring and replenishment |
| Fulfillment | Delivery System | Delivery SLA and delay monitoring |
| Marketing | Marketing Platform | Campaign performance analysis |

---

## Current Extraction Challenges

- Data is exported manually or semi-manually.
- File formats vary across systems.
- Some systems use different product and customer identifiers.
- Data arrives at different times, causing reporting delays.
- There is no centralized raw data landing zone.
- Real-time events are not captured in a consistent way.
- Business teams maintain separate spreadsheet logic.

---

## Current-State Assumptions

Because this is a simulated engagement, the source system landscape is based on realistic retail data modernization patterns.

In a real client engagement, this document would be validated through:

- Stakeholder interviews
- Source system access review
- Sample data profiling
- Schema discovery
- Existing report review
- Data owner confirmation

---

## Leadership Interpretation

The source system landscape helps the Engagement & Technical Lead understand the current data ecosystem before proposing technical solutions.

It prevents the team from designing Azure pipelines without knowing where data comes from, who owns it, and what problems currently exist.