# Storage Account Naming Convention

## Project

RetailPulse Azure Data Engagement Platform

## Purpose

This document defines the Azure Storage Account naming convention for the RetailPulse Azure data platform.

Azure Storage Accounts will support the data lake structure for Bronze, Silver, and Gold layers.

---

## Important Naming Constraint

Azure Storage Account names must be globally unique and have strict naming requirements.

To keep names simple and compliant, the naming pattern avoids hyphens and special characters.

---

## Naming Pattern

```text
st<project><workload><env><region><suffix>