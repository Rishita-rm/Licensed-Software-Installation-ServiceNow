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
```

---

## System Architecture

```text
Service Catalog
       │
       ▼
Catalog Item (Software Installation Request)
       │
       ▼
Variables:
- Software Name
- Version Required
- License Justification
- Urgency
       │
       ▼
Flow Designer Workflow
       │
       ├── Approval Step
       │
       └── Create Catalog Task
                │
                ▼
Assigned to Software Support Team
```

---

## Data Flow

This solution uses standard ServiceNow request-related tables:

- **sc_request** → Request (REQ)
- **sc_req_item** → Requested Item (RITM)
- **sc_task** → Catalog Task (SCTASK)

These records work together to track the full request lifecycle from submission to completion.

---

## Catalog Variables

The catalog item includes the following fields:

| Variable Name | Type | Purpose |
|---|---|---|
| Software Name | Single Line Text | Captures the name of the requested software |
| Version Required | Single Line Text | Captures the required software version |
| License Justification | Multi Line Text | Explains why the software is needed |
| Urgency | Choice | Indicates request priority level |

### Example Urgency Options

- Normal
- High
- Critical

---

## Workflow Automation

The automation was built using **Flow Designer**.

### Trigger

- Request is submitted from the Service Catalog

### Main Steps

1. Start when the catalog request is created
2. Capture the submitted request details
3. Send the request for approval
4. Create a catalog task after approval
5. Assign the task to the **Software Support Team**
6. Track the request until fulfillment is complete

---

## Field Validation and Automation

To improve data quality and reduce manual errors, the project includes validation and auto-population logic.

### Mandatory Fields

The following fields are required:

- Software Name
- Version Required
- License Justification

### Automatic Population

- **Requested For** uses the logged-in user
- **Department** and **Location** can be pulled from the user profile
- Request details flow into the corresponding fulfillment task

---

## Testing and Validation

The solution was tested to ensure the workflow performs correctly from start to finish.

### Test Cases

- Request (**REQ**) is created successfully
- Requested Item (**RITM**) is generated
- Catalog Task (**SCTASK**) is created correctly
- Task is assigned to the Software Support Team
- Submitted variables appear correctly in the request record
- Workflow progresses through the expected stages

### Expected Result

A software request moves from submission to approval, task creation, assignment, and completion without manual process breakdown.

---

## Update Set Deployment

To support migration and reuse, the project was prepared for deployment through Update Sets.

### Deployment Steps

1. Mark the Update Set as **Complete**
2. Export the Update Set as **XML**
3. Import it into the target ServiceNow instance
4. Preview the changes
5. Commit the Update Set successfully

This makes the solution portable and easier to implement in other environments.

---

## Project Structure

```text
Global-Rise-Skills-main/
├── Documentation/
│   ├── Phasr4/
│   │   ├── ServiceNow_Project_Documentation.docx
│   │   ├── ServiceNow_Software_Request_Project (1).docx
│   │   └── servicenow_licensed_software_installation.docx
│   └── phase5/
│       └── Conclusion.md
├── ScreenShots/
│   ├── Phase2/
│   │   ├── Business Rules/
│   │   └── Data Architecture/
│   ├── Phase3/
│   └── Phase4/
├── VIdeos/
│   └── servicesnow.mp4
└── LICENSE
```

---

## Screenshots

This repository includes screenshots from different project phases, including:

- catalog item setup
- variables configuration
- data architecture
- flow/workflow setup
- task creation
- approval flow
- testing and result validation

You can find them inside the **ScreenShots/** folder.

---

## Technologies Used

- ServiceNow
- Service Catalog
- Flow Designer
- Catalog Variables
- Approval Workflow
- Catalog Tasks
- Update Sets

---

## Use Case

This project is useful for organizations that want to manage software installation requests in a more structured and automated way.

### Example Use Case

An employee needs licensed software for work. Instead of sending emails manually, the employee submits a request through ServiceNow. The request is reviewed, approved, assigned to IT, and completed using a standardized process.

---

## Benefits

- Faster request handling
- Better visibility into request status
- Reduced manual work
- Improved approval control
- Organized fulfillment process
- Reusable ServiceNow configuration
- Better communication between employees and IT

---

## Future Improvements

Possible enhancements for this project include:

- multi-level approvals
- software asset availability checks
- automated notifications
- SLA tracking
- dashboard reporting
- license inventory integration
- role-based approval logic
- security review for high-risk software

---

## Conclusion

This project successfully implements a reliable and user-friendly ServiceNow solution for managing software installation requests.

By using the Service Catalog, Flow Designer, and structured request records, the system improves efficiency, reduces manual effort, and provides better control over software request fulfillment. The solution is scalable, reusable, and suitable for deployment across ServiceNow instances using Update Sets.

---

## License

This project is licensed under the terms of the MIT License. See the LICENSE file for more details.
