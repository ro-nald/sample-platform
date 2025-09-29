# Sample platform

A tool for developers to deploy their applications to an Azure Service Plan managed by a Platform Team.

Using the GitHub CLI, the GitHub Actions workflow can deploy an application as an App Service to the App Services plan which is configured in this repo.

> [!NOTE] This repository is still in active development and may not yet provide the Features stated in this document.

## Usage

As a demo project, the instructions provided are to run on a personal forked copy of this GitHub repository.

## Features

- GitHub Actions workflows
  - Manual workflows intended to be triggered by developers using the GitHub CLI.
  - Automatic workflows to continuously deploy new infrastructure.
  - Approval-based workloads for provisioning Platform resources.
- Provisioning of App Service Plan to be used by development teams.
- Workflow-based deployment of application to the user's Azure cloud estate.

---

## Setting up the platform

### Platform setup requirements

1. User has a GitHub Account and installed the GitHub Actions CLI and authenticating with their GitHub credentials.
2. User has forked this repository.

### Platform setup instructions

1. After forking the repository, configure Microsoft Azure authentication for GitHub Actions workers to be able to provision resources on Azure.
2. Manually run the associated pipeline to provision the initial resources.

---

## Using the platform

### Platform usage requirements

1. User has a GitHub Account and installed the GitHub Actions CLI and authenticating with their GitHub credentials.
2. User has Python application code which is another GitHub repository.

### Platform usage instructions

1. The developer manually triggers the GitHub Actions workflow to deploy the App Service using the GitHub CLI, providing the URL of the repository.
2. The developer will await approval from a member of the approvers list. The developer may choose to self-approve the workflow run.
3. The developer can find the publically available URL of the deployed App Service in the output of the pipeline.

---

## Upcoming Features

### External

- Budgeting configuration template
- Monitoring configuration template
- Logging configuration template
- Database configuration template
- Azure Storage configuration template
- Email alerts for application deployment completion

### Internal

- Only allow 'demo' applications to last for a maximum of 1 hour before being destroyed.
- Introduce an overall budget for the platform.
- Create a mechanism for upgrading the App Service Plan whilst maintaining App Availability, and producing a report to state availability during the transition.
