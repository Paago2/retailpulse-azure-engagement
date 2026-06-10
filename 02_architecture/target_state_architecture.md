# Target-State Azure Architecture

## Project

RetailPulse Azure Data Engagement Platform

## Client

Northwind Retail Group

## Architecture Objective

Design a modern Azure-based data platform that supports batch ingestion, real-time streaming, curated analytics, Power BI reporting, governance, monitoring, and future AI/ML readiness.

The target architecture is designed to solve the client's current challenges around disconnected data sources, delayed reporting, inconsistent KPI definitions, limited governance, and lack of real-time operational visibility.

## High-Level Architecture

```text
Source Systems
    |
    |-- Batch Sources
    |     - Customer data
    |     - Product data
    |     - Store data
    |     - Inventory data
    |     - Marketing campaign data
    |
    |       Azure Data Factory
    |              |
    |              v
    |       ADLS Gen2 Bronze Layer
    |
    |-- Streaming Sources
          - Order created events
          - Payment completed events
          - Order packed events
          - Order shipped events
          - Order delivered events
          - Order cancelled events

            Azure Event Hubs
                  |
                  v
            Stream Processing
            Azure Databricks or Azure Stream Analytics
                  |
                  v
            ADLS Gen2 Bronze Layer

Bronze Layer
    |
    v
Silver Layer
    - Cleaned data
    - Standardized schemas
    - Deduplicated records
    - Validated business keys
    - Data quality checks

Silver Layer
    |
    v
Gold Layer
    - Fact tables
    - Dimension tables
    - KPI-ready reporting models
    - Aggregated business metrics

Gold Layer
    |
    v
Power BI
    - Executive dashboard
    - Operational dashboard
    - Inventory dashboard
    - Data quality dashboard

Governance and Operations
    - Microsoft Purview
    - Azure Key Vault
    - RBAC
    - Azure Monitor
    - Azure DevOps Boards