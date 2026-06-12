# Cost-Control Checklist

## Project

RetailPulse Azure Data Engagement Platform

## Purpose

This checklist is used before, during, and after Azure resource deployment to prevent unnecessary cloud spend.

---

## Pre-Deployment Checklist

Before deploying any paid Azure resource:

- [ ] Is the resource required for the current sprint?
- [ ] Is there a lower-cost local or documentation-first alternative?
- [ ] Has the resource group been defined?
- [ ] Has the environment been identified?
- [ ] Are required tags defined?
- [ ] Is the resource owner identified?
- [ ] Is the expected cost understood?
- [ ] Is a budget or alert strategy in place?
- [ ] Is there a cleanup plan?
- [ ] Is approval needed before deployment?

---

## Resource Creation Checklist

When creating a resource:

- [ ] Use approved naming convention
- [ ] Use approved region
- [ ] Use lowest practical SKU/tier for dev
- [ ] Apply required tags
- [ ] Avoid premium tiers unless justified
- [ ] Configure auto-shutdown or auto-termination when available
- [ ] Disable public access where appropriate
- [ ] Document the resource purpose
- [ ] Link the work to an Azure Boards task

---

## Daily Cost-Control Checklist

During active cloud development:

- [ ] Check active resources
- [ ] Stop unused compute
- [ ] Confirm Databricks clusters are not idle
- [ ] Confirm test event producers are stopped
- [ ] Confirm unnecessary triggers are disabled
- [ ] Review obvious cost anomalies
- [ ] Confirm no unexpected resources were created

---

## End-of-Sprint Checklist

At the end of each sprint:

- [ ] Review Azure costs by resource group
- [ ] Review resources by tag
- [ ] Delete temporary resources
- [ ] Stop or scale down compute
- [ ] Disable unused triggers
- [ ] Review Log Analytics ingestion
- [ ] Remove unused test secrets
- [ ] Update cleanup notes
- [ ] Confirm remaining resources are needed for next sprint

---

## High-Risk Resource Checklist

Before using high-risk services:

### Databricks

- [ ] Use smallest practical cluster
- [ ] Enable auto-termination
- [ ] Stop cluster after use
- [ ] Avoid long-running interactive clusters

### Synapse Dedicated SQL Pool

- [ ] Confirm dedicated pool is necessary
- [ ] Prefer serverless or alternative for early testing
- [ ] Pause when not in use
- [ ] Monitor compute time

### Event Hubs

- [ ] Use controlled event volume
- [ ] Use lowest suitable tier
- [ ] Limit retention for dev
- [ ] Stop event producer scripts after testing

### Log Analytics

- [ ] Avoid excessive debug logs
- [ ] Set appropriate retention
- [ ] Review ingestion volume

---

## Approval Checklist

Before production deployment:

- [ ] Architecture approved
- [ ] Security reviewed
- [ ] Cost estimate reviewed
- [ ] Budget alerts configured
- [ ] Support plan defined
- [ ] Rollback plan documented
- [ ] Ownership confirmed

---

## Leadership Interpretation

A cost-control checklist turns cost awareness into a repeatable operating habit.

It helps the team avoid a common cloud mistake: creating resources quickly without clear ownership, budget visibility, or cleanup discipline.