# ServiceNow Software Installation Request Automation

A ServiceNow Service Catalog project that automates the process of requesting, approving, and fulfilling software installation requests. This solution provides a structured workflow for employees to submit software requests while allowing IT teams to review, approve, assign, and track each request through completion.

---

## Project Overview

The **Software Installation Request Automation** project was built in ServiceNow to simplify and standardize the process of software installation requests within an organization.

Instead of handling requests manually, employees can submit a request through a catalog item in the **Service Catalog**. The request is then processed through an automated workflow that creates the necessary records, routes approvals, and assigns fulfillment tasks to the appropriate IT support team.

This project improves:
- request tracking
- approval management
- task assignment
- process consistency
- overall service delivery efficiency

---

## Business Objective

The main objective of this project is to automate the software request lifecycle in ServiceNow.

### Goals
- Automate the software installation request process
- Ensure approvals are captured before installation
- Reduce manual effort in task creation and assignment
- Improve visibility into request progress
- Maintain structured request data across ServiceNow tables
- Create a scalable and reusable ServiceNow solution

---

## Key Features

- **Service Catalog Item** for software installation requests
- **Custom Variables** to capture request details
- **Flow Designer Automation** for request processing
- **Approval Workflow** for controlled software access
- **Catalog Task Creation** for fulfillment
- **Assignment Group Routing** to IT Software Support
- **Request Tracking** using REQ, RITM, and SCTASK records
- **Testing and Validation** to verify workflow success
- **Update Set Deployment** for migration to other instances

---

## System Workflow

The project follows the workflow below:

```text
User submits request
        ↓
Request Record Created (REQ)
        ↓
Requested Item Created (RITM)
        ↓
Manager / Approval Step
        ↓
Catalog Task Created (SCTASK)
        ↓
Assigned to Software Support Team
        ↓
Software Installation Completed
