---
icon: layer-plus
---

# Task Tracker Terraform Mini Projekt

A simple Task Tracker with REST API Backend and Angular Frontend using Buhler Components. Infrastructure Setup on Azure with Terraform. The Code is hosted on the andrin-playground DevOps Project. CI/CD integration using azure pipelines for deployment. Potential extension could be integrating SonarQube and Dependency Track.&#x20;

### Infrastructure (via Terraform)

I will deploy these **Azure resources**:

* `Resource Group`
* `App Service Plan`
* `App Service` (for API)
* `Static Web App` or another `App Service` (for Angular)
* `SQL Server` + `SQL Database`
* _(Optional)_: `Application Insights`, `Key Vault`

***

### &#x20;Azure DevOps Setup

* Project with Repos & Pipelines
* Service Connection to Azure
* Pipelines:
  * `terraform-pipeline.yml`: Deploy infrastructure
  * `api-pipeline.yml`: Build & deploy .NET API
  * `frontend-pipeline.yml`: Build & deploy Angular app

***

### Code Requirements

#### **Backend (.NET API)**

* CRUD endpoints for Tasks (`GET`, `POST`, `PUT`, `DELETE`)
* SQL DB connection (Entity Framework)
* Task model: `Id`, `Title`, `IsCompleted`, `DueDate`

#### **Frontend (Angular)**

* Task list, task form, task item components
* Angular service to call the API
* Routing setup
