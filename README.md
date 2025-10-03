# DisasterAlleviation_Part2-main
Overview

This project is developed as part of the APPR6312 Portfolio of Evidence (Part 2).
It is a prototype web system for the Disaster Alleviation Foundation that supports:

User Registration and Login (with ASP.NET Core Identity and optional Azure AD integration)

Disaster Incident Reporting

Resource Donation and Distribution Tracking

Volunteer Management

Automated Build, Test, and Deployment using Azure Repos and Azure Pipelines

Technologies Used

Visual Studio 2022 (latest version with ASP.NET and Azure Development workloads)

.NET 7/8 SDK (latest stable release)

ASP.NET Core MVC with Entity Framework Core

Azure SQL Database for persistent storage

Azure App Service for hosting

Azure Repos (Git) for version control

Azure Pipelines for CI/CD

xUnit / MSTest for automated unit testing

Azure Load Testing for performance validation

Project Structure
/DisasterAlleviationFoundation
│   README.md
│   azure-pipelines.yml
│
├── WebApp/                # ASP.NET Core MVC frontend & APIs
├── Core/                  # Domain models and interfaces

Features Implemented

User Registration & Login

ASP.NET Core Identity (local accounts)

Optional Azure AD authentication for production

Disaster Incident Reporting

Create, view, update, delete incidents

Linked to authenticated users

Resource Donation & Distribution

Donations tracked by type, quantity, and distribution status

Volunteer Management

Volunteer registration and task assignment

Branching Strategy

We use a Gitflow-inspired workflow in Azure Repos:

main → Production-ready code

develop → Integration branch for tested features

feature/xyz → Feature-specific branches

Example:

git checkout -b feature/incident-report
git push -u origin feature/incident-report


Pull Requests are required before merging into develop or main.

Continuous Integration & Deployment (CI/CD)
Azure Pipelines

CI/CD is configured via azure-pipelines.yml.
Pipeline steps include:

Restore dependencies

Build solution in Release mode

Run unit and integration tests

Publish build artifacts

Deploy to Azure App Service (Test slot → Production slot)

Deployment is automatic when changes are merged into main.
Manual approval is required for production deployment.

Testing Strategy

Unit Tests → xUnit / MSTest to validate business logic

Integration Tests → ASP.NET Core TestServer with EF Core InMemory database

Load & Stress Tests → Azure Load Testing simulating concurrent user traffic

UI Tests → Playwright or Selenium (optional)

Usability Tests → Small group testing with feedback

To run tests:

dotnet test

Load Testing (Optional Marks)

Load and stress testing executed using Azure Load Testing with scenarios:

Incident reporting under 100 concurrent users

Donation processing under stress

Reports are attached in the documentation folder.

Deployment

Deployed to Azure App Service:

Test Environment → https://<appname>-test.azurewebsites.net

Production Environment → https://<appname>.azurewebsites.net

Deliverables for POE Submission

Link to Azure Repos repository

Screenshots of branching, pull requests, and pipeline runs

azure-pipelines.yml file

Test results (unit, integration, load)

Deployed application link (test or production slot)

Authors

Developed by Mualusi

Submitted for APPR6312 Portfolio of Evidence (Part 2)
├── Infrastructure/        # EF Core DbContext and repositories
├── Tests/                 # Unit and integration tests
└── Migrations/            # EF Core migrations
