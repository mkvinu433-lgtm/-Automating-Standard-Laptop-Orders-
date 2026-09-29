# Streamlining IT Procurement: Automating Standard Laptop Orders with Flow Designer

## Project Overview

This project automates the procurement and configuration workflow for standard laptop orders using **ServiceNow Flow Designer**.

The workflow is designed to reduce manual intervention, improve task assignment, and ensure that standard laptop requests are promptly sent to the Hardware team for configuration.

## Problem Statement

The existing IT procurement process involves manual steps when handling standard laptop requests. Configuration tasks can be overlooked or delayed, resulting in longer user wait times and inefficient use of IT resources.

This project addresses the problem by creating an automated workflow that generates and assigns a catalog task to the Hardware team after the service request receives approval.

## User Story

> As a member of the IT procurement team, I want a streamlined process for ordering standard laptops so that tasks are automatically generated and assigned to the Hardware team for configuration.

This helps ensure that laptops are configured promptly after arrival, reducing user wait times and manual intervention.

## Project Objectives

- Create a seamless experience for users requesting standard laptops.
- Ensure timely laptop configuration.
- Reduce manual intervention and potential errors.
- Improve resource utilization within the IT department.
- Optimize task allocation.
- Improve efficiency and productivity in IT procurement operations.

## Technology / Platform

- **Platform:** ServiceNow
- **Automation Tool:** Flow Designer
- **Application:** Global
- **Run As:** System User
- **Service Catalog:** Standard Laptop
- **Assignment Group:** Hardware

## Workflow

```text
User
  |
  v
Service Catalog
  |
  v
Standard Laptop Request
  |
  v
Approval
  |
  v
Flow Designer
  |
  v
Create Catalog Task
  |
  v
Assignment Group: Hardware
  |
  v
Laptop Configuration
```

## Implementation

### Milestone 1: Create the Flow

Create a Flow Designer flow named:

**Standard Laptop Task**

Steps:

1. Open ServiceNow.
2. Go to **All** and search for **Flow Designer**.
3. Open **Flow Designer** under Process Automation.
4. Select **New → Flow**.
5. Set the Flow Name to `Standard Laptop Task`.
6. Set the Application to `Global`.
7. Select `System User` as the Run As user.
8. Submit the flow.
9. Add a trigger.
10. Search for and select **Service Catalog** as the trigger.
11. Click **Done**.

### Create Catalog Task Action

Under **Actions**:

1. Click **Add an Action**.
2. Search for **Create Catalog Task**.
3. Select the **Create Catalog Task** action.
4. Drag and drop the **Requested Item Record** into the Request Item field.
5. The table is populated as **Catalog Task**.
6. Set the Short Description to:

   `Laptop need to Configured`

7. Add the Description field with the same value.
8. Set the Assignment Group to:

   `Hardware`

9. Set the Approval field to:

   `Approved`

10. Leave the remaining fields as default.
11. Click **Done**.
12. Save the Flow.
13. Activate the Flow.

## Milestone 2: Flow Assignment

The created flow must be assigned to the Standard Laptop service catalog item.

1. Open ServiceNow.
2. Go to **All** and search for **Maintain Items**.
3. Open **Maintain Items**.
4. Search for the **Standard Laptop** catalog item.
5. Open the Standard Laptop record.
6. Go to **Process Engine**.
7. Remove the remaining automations.
8. Add the Flow.
9. Select the flow:

   `Standard Laptop Task`

10. Save the record.

## Milestone 3: Service Catalog

The Standard Laptop service catalog item is used to place the request and obtain approval.

1. Go to **All**.
2. Search for **Service Catalog**.
3. Open **Service Catalog → Hardware**.
4. Find **Standard Laptop**.
5. Select **Order Now** to place the request.
6. View the order status.
7. Open the Request Number.
8. Scroll to the **Approvers** section.
9. Approve the request.
10. Open the **Requested Item** section.
11. Open the Requested Item record.
12. Scroll to the **Catalog Tasks** section.
13. Open the catalog task to verify the updated status, short description, and assignment group.

## Expected Result

After the Standard Laptop request is approved, Flow Designer automatically creates a Catalog Task with:

- **Short Description:** Laptop need to Configured
- **Description:** Laptop need to Configured
- **Assignment Group:** Hardware
- **Approval:** Approved

This allows the Hardware team to receive the configuration task without requiring additional manual task creation.

## Benefits

- Reduces manual procurement activities.
- Helps prevent configuration tasks from being overlooked.
- Automatically assigns configuration work to the Hardware team.
- Reduces user waiting time.
- Improves resource allocation.
- Provides a more streamlined procurement workflow.

## Project Structure

```text
Streamlining-IT-Procurement/
│
├── README.md
└── Project Documentation
```

## Conclusion

By automating the standard laptop procurement process with ServiceNow Flow Designer, the project streamlines the workflow and reduces manual overhead. The automated process helps ensure timely laptop configuration, minimizes user wait times, and improves productivity within the IT department.

The solution also supports better resource allocation and provides users with a more efficient procurement experience.
