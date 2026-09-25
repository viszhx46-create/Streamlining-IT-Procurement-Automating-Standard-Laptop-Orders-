# Streamlining IT Procurement: Automating Standard Laptop Orders with Flow Designer

## Overview

This project documents a ServiceNow Flow Designer automation for standard laptop procurement.

The goal is to automate the creation and assignment of a Catalog Task after a standard laptop request is approved, so the Hardware team can configure the laptop promptly.

## Problem Statement

The existing IT procurement process involves manual work and can cause delays when standard laptop requests require configuration. The project automates this part of the process to reduce manual intervention and improve task allocation.

## User Story

> As a member of the IT procurement team, I want a streamlined process for ordering standard laptops so that tasks are automatically generated and assigned to the hardware team for configuration.

## Project Objectives

- Create a seamless experience for users requesting standard laptops.
- Reduce manual intervention and potential errors.
- Improve resource utilisation through automated task allocation.
- Enhance efficiency and productivity in IT procurement operations.

## Implementation

### Milestone 1 — Create the Flow

Create a Flow Designer flow named **Standard Laptop Task**.

Configuration:

- Application: `Global`
- Run as: `System user`
- Trigger: `Service Catalog`
- Action: `Create Catalog Task`
- Requested Item Record: use the requested item record from the trigger
- Short description: `Laptop need to Configured`
- Description: `Laptop need to Configured`
- Assignment group: `Hardware`
- Approval: `Approved`

After configuring the action:

1. Save the flow.
2. Activate the flow.

### Milestone 2 — Assign the Flow to the Service Catalog Item

1. Open ServiceNow.
2. Go to **All > Maintain Items**.
3. Search for **Standard Laptop**.
4. Open the Standard Laptop record.
5. Open **Process engine**.
6. Remove the remaining automations.
7. Add the **Standard Laptop Task** flow.
8. Save the record.

### Milestone 3 — Test Through the Service Catalog

1. Go to **All > Service Catalog**.
2. Open **Hardware**.
3. Select **Standard Laptop**.
4. Click **Order Now**.
5. Open the order status.
6. Open the Request Number.
7. Scroll to the **Approvers** section.
8. Approve the request.
9. Open the **Requested Item**.
10. Scroll to **Catalog Tasks**.
11. Open the catalog task and verify the updated status, short description, and assignment group.

## Expected Result

After the Standard Laptop request is approved, a Catalog Task is created automatically with:

- **Short description:** Laptop need to Configured
- **Description:** Laptop need to Configured
- **Assignment group:** Hardware
- **Approval:** Approved

This allows the Hardware team to receive the configuration task without requiring the procurement team to create it manually.

## Project Structure

```text
servicenow-standard-laptop-flow/
├── README.md
├── docs/
│   └── implementation.md
└── screenshots/
    └── .gitkeep
```

## Documentation

Detailed implementation notes are available in `docs/implementation.md`.

## Source

This repository documentation is based on the provided project document, **Streamlining IT Procurement: Automating Standard Laptop Orders with Flow Designer**.
