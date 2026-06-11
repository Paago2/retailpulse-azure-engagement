# Required Pipeline Secrets

## Project

RetailPulse Azure Data Engagement Platform

## Purpose

This document identifies the types of secrets, credentials, keys, and connection values that may be required by the RetailPulse Azure data platform.

The goal is to prevent secrets from being stored in code, notebooks, local files, or pipeline definitions.

---

## Secret Management Principle

No secret should be hardcoded in:

- Source code
- Markdown files
- Git commits
- Databricks notebooks
- ADF pipeline JSON
- Power BI files
- Local `.env` files committed to source control
- Azure DevOps pipeline YAML

Secrets should be stored in Azure Key Vault or a secure approved secret store.

---

## Potential Secret Categories

| Secret Category | Example | Used By | Storage Location |
|---|---|---|---|
| Storage access credential | Storage account key, SAS token, connection string | ADF, Databricks, pipelines | Azure Key Vault |
| Event Hubs connection | Event Hub connection string | Event producer, streaming consumer | Azure Key Vault |
| Database credential | SQL username/password or connection string | ADF, Databricks, reporting layer | Azure Key Vault |
| Service principal credential | Client secret or certificate | Terraform, CI/CD, service automation | Azure Key Vault / pipeline secret store |
| API key | External source API key | Batch ingestion pipeline | Azure Key Vault |
| Power BI service principal secret | Power BI deployment automation | CI/CD or deployment script | Azure Key Vault |
| Databricks token | Databricks API automation | CI/CD or admin operations | Azure Key Vault |
| SMTP/webhook secret | Alert notification integration | Monitoring and support workflows | Azure Key Vault |

---

## Preferred Authentication Approach

Where possible, prefer managed identity over static secrets.

Recommended order:

1. Managed identity
2. Federated identity / workload identity
3. Certificate-based service principal
4. Client secret only when necessary
5. Storage keys or SAS tokens only for limited cases

---

## Secrets Needed by Workstream

| Workstream | Possible Secret Needed | Notes |
|---|---|---|
| Batch ingestion | Source system credentials, storage access | Use ADF managed identity where possible |
| Streaming ingestion | Event Hubs connection string or managed identity | Prefer Azure AD authentication where supported |
| Transformation | Storage access, Databricks secrets | Prefer managed identity / secret scope |
| Power BI | Service principal secret if automating deployment | Avoid storing credentials in PBIX files |
| Terraform / IaC | Azure service principal or OIDC configuration | Prefer OIDC/federated credentials over long-lived secrets |
| Monitoring | Webhook keys or notification secrets | Store securely and restrict access |

---

## Do Not Store These in Git

The following should never be committed:

```text
.env
*.pem
*.key
secrets.json
connection_strings.json
terraform.tfvars with secrets
service_principal_credentials.json
storage_account_keys.txt
eventhub_connection_string.txt