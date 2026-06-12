# Resource Cleanup Policy

## Project

RetailPulse Azure Data Engagement Platform

## Purpose

This document defines the cleanup policy for Azure resources used in the RetailPulse Azure data modernization engagement.

The goal is to avoid orphaned resources, unnecessary cloud spend, and unmanaged test environments.

---

## Cleanup Principle

Every Azure resource should have:

1. A clear owner
2. A defined environment
3. Required tags
4. A known purpose
5. A retention expectation
6. A cleanup decision

---

## Resource Lifecycle

```text
Plan resource
    ↓
Create resource with tags
    ↓
Use resource for sprint work
    ↓
Review at end of sprint
    ↓
Keep, stop, scale down, or delete