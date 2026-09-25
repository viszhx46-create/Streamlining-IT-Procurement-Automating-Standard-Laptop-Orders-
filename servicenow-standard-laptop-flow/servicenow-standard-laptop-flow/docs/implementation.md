# Implementation Guide

## 1. Flow Creation

Create a new Flow in ServiceNow Flow Designer.

**Flow properties**

| Property | Value |
|---|---|
| Flow Name | Standard Laptop Task |
| Application | Global |
| Run as | System user |

Add a **Service Catalog** trigger.

Then add the **Create Catalog Task** action.

### Create Catalog Task configuration

| Field | Value |
|---|---|
| Request item | Requested Item Record |
| Table | Catalog Task |
| Short description | Laptop need to Configured |
| Description | Laptop need to Configured |
| Assignment group | Hardware |
| Approval | Approved |

Save and activate the flow.

## 2. Service Catalog Assignment

Open **Maintain Items** and locate **Standard Laptop**.

Under **Process engine**, remove the remaining automations and add the **Standard Laptop Task** flow.

Save the Standard Laptop record.

## 3. Validation

Place a Standard Laptop order through:

`Service Catalog > Hardware > Standard Laptop > Order Now`

Approve the request and open the Requested Item.

Under **Catalog Tasks**, verify that the task has been created and that the short description and assignment group are updated as configured.

## Note

This repository contains documentation for the ServiceNow configuration. The actual Flow Designer configuration must be created inside a ServiceNow instance.
