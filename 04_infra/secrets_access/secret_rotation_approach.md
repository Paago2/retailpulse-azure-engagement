# Secret Rotation Approach

## Project

RetailPulse Azure Data Engagement Platform

## Purpose

This document defines the secret rotation approach for the RetailPulse Azure data platform.

The goal is to reduce the risk of long-lived credentials, expired secrets, leaked credentials, and operational outages caused by unmanaged secrets.

---

## Secret Rotation Principle

Secrets should be:

- Stored securely
- Accessed only by approved identities
- Rotated on a defined schedule
- Rotated immediately if exposure is suspected
- Replaced with managed identity where possible
- Removed when no longer needed

---

## Rotation Priority

| Secret Type | Priority | Reason |
|---|---|---|
| Production service principal secrets | High | Broad automation impact |
| Storage account keys | High | Can expose data access |
| Event Hub connection strings | High | Can allow event publishing/reading |
| External API keys | Medium to High | Depends on data sensitivity |
| Webhook secrets | Medium | Can trigger integrations or notifications |
| Dev/test credentials | Medium | Lower impact but still risky |
| Temporary test secrets | Low to Medium | Should be deleted quickly |

---

## Recommended Rotation Schedule

| Secret Type | Suggested Rotation |
|---|---|
| Production client secrets | Every 90 days or per policy |
| Dev/test client secrets | Every 180 days or per policy |
| Storage account keys | Avoid where possible; rotate if used |
| Event Hub connection strings | Every 90–180 days or after personnel/system changes |
| API keys | Based on provider policy or every 90–180 days |
| Temporary secrets | Delete immediately after use |

---

## Rotation Workflow

```text
Identify secret due for rotation
    ↓
Create replacement secret
    ↓
Store replacement in Key Vault
    ↓
Update consuming service or identity reference
    ↓
Validate pipeline/application works
    ↓
Disable old secret
    ↓
Monitor for failures
    ↓
Delete old secret after safe period
    ↓
Document rotation completed