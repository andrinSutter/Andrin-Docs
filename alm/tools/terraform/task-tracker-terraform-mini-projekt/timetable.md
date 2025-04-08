---
icon: calendar-days
---

# Timetable

### 📅 **Day 1 – Tuesday, April 8**

**1. Infrastructure Setup (Terraform) –&#x20;**_**3 hours**_

* Set up Terraform folder and provider
* Define Azure resources: Resource Group, App Services, SQL DB
* Deploy with `terraform init`, `plan`, and `apply`

**2. Azure DevOps Setup –&#x20;**_**2–3 hours**_

* Create DevOps project (`andrin-playground`)
* Create service connection to Azure
* Write & test `terraform-pipeline.yml`

**3. Optional Finishing or Buffer –&#x20;**_**2 hours**_

* Troubleshooting, polish Terraform config
* Test Azure resource accessibility (e.g., check App Services, SQL)

***

### 📅 **Day 2 – Wednesday, April 9**

**4. Backend Development (.NET API) –&#x20;**_**5 hours**_

* Scaffold project and set up model: `Id`, `Title`, `IsCompleted`, `DueDate`
* Add EF Core with SQL DB connection
* Build CRUD endpoints (GET, POST, PUT, DELETE)

**5. API Deployment –&#x20;**_**2–3 hours**_

* Create and test `api-pipeline.yml`
* Deploy API to Azure App Service
* Test with Swagger/Postman

***

### 📅 **Day 3 – Thursday, April 10**

**6. Frontend Development (Angular) –&#x20;**_**5–6 hours**_

* Generate Angular project
* Create components: task list, form, item
* Implement Angular service to call the API
* Add basic routing

**7. Frontend Deployment –&#x20;**_**2–3 hours**_

* Create and run `frontend-pipeline.yml`
* Deploy Angular app to Azure Static Web App or App Service
* Test full frontend-to-backend connection
