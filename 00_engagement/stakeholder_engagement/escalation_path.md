# Escalation Path

## Project

RetailPulse Azure Data Engagement Platform

## Purpose

This document defines how risks, blockers, issues, and decisions are escalated during the engagement.

The goal is to ensure that blockers are visible early and routed to the correct owner before they impact sprint delivery or business outcomes.

---

## Escalation Principles

1. Escalate early, not late.
2. Document the issue clearly.
3. Identify impact, owner, and decision needed.
4. Communicate through the correct channel.
5. Track resolution in Azure Boards or the risk register.
6. Close the escalation only after the blocker is resolved or accepted.

---

## Severity Levels

| Severity | Description | Example | Response Target |
|---|---|---|---|
| Sev 1 | Critical blocker impacting delivery or production | Azure access unavailable for core team; production data exposure risk | Same day |
| Sev 2 | High-impact issue affecting sprint commitment | Data source unavailable; security approval delayed | 1 business day |
| Sev 3 | Moderate issue with workaround available | Sample data schema changed; dashboard requirement unclear | 2–3 business days |
| Sev 4 | Low-impact question or clarification | Naming convention question; documentation update needed | Within sprint |

---

## Escalation Matrix

| Issue Type | First Owner | Escalate To | Final Decision Owner |
|---|---|---|---|
| Scope change | Engagement Lead | Executive Sponsor | Executive Sponsor |
| Technical architecture blocker | Tech Lead | Cloud/Data Architect | Tech Lead |
| Azure access issue | Cloud Engineer | Security/Governance Lead | Security Sponsor |
| Data quality issue | Data Engineer | Governance Lead | Data Owner |
| BI requirement conflict | BI Lead | Business Owner | Product/Business Sponsor |
| Cost overrun risk | Cloud Engineer | Engagement Lead | Executive Sponsor |
| Security or compliance concern | Security Lead | Security Sponsor | Security Sponsor |
| Sprint delivery delay | Task Owner | Engagement Lead | Engagement Lead |

---

## Escalation Workflow

```text
Issue identified
    ↓
Task owner documents blocker
    ↓
Engagement Lead reviews impact
    ↓
Correct owner assigned
    ↓
Mitigation plan created
    ↓
Stakeholders informed if needed
    ↓
Issue tracked to resolution
    ↓
Escalation closed