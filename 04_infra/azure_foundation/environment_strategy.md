# Environment Strategy

## Project

RetailPulse Azure Data Engagement Platform

## Purpose

This document defines the environment strategy for the RetailPulse Azure data modernization engagement.

The goal is to separate development, testing, and production responsibilities so the platform can be built safely and maintained consistently.

---

## Recommended Environments

| Environment | Purpose |
|---|---|
| dev | Development, experimentation, early pipeline testing, sample data |
| test | Integration testing, validation, user acceptance testing |
| prod | Production workloads and business-facing reporting |

---

## Environment Progression

```text
dev → test → prod