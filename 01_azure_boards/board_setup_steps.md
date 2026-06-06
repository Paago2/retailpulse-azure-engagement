# Azure Boards Setup Steps

## Objective

Create an Azure DevOps Boards project to manage the RetailPulse Azure Data Engagement Platform.

## Recommended Setup

- Organization: Personal Azure DevOps organization
- Project Name: RetailPulse Azure Engagement
- Visibility: Private
- Process: Agile
- Version Control: Git
- Work Item Hierarchy: Epic → Feature → User Story → Task

## Manual Setup Steps

1. Go to Azure DevOps
2. Create a new organization if one does not already exist
3. Create a new project
4. Set project name to RetailPulse Azure Engagement
5. Set visibility to Private
6. Select Git for version control
7. Select Agile as the work item process
8. Open Boards → Backlogs
9. Enable Epics and Features if not visible
10. Create Epics from the project workstreams
11. Create Features under Epics
12. Create User Stories under Features
13. Create Tasks under User Stories
14. Configure iterations/sprints
15. Capture screenshots for documentation

## Cost-Control Notes

Azure DevOps Boards does not require deploying Azure cloud infrastructure.

Cost risk is low if:
- The project uses the free Azure DevOps tier
- Users are kept within free Basic user limits
- No paid Test Plans are enabled
- No unnecessary Azure Pipelines hosted-agent usage is triggered
- No Azure cloud resources are deployed yet