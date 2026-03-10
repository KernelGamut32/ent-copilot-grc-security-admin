
# Lab 1.5 — Review Unified Audit Log for Power Platform Events

## Course

Enterprise Copilot Governance, Security, and Administration

## Lab Duration

~60 minutes

## Lab Objective

In this lab you will investigate **Power Platform administrative activity using the Microsoft Purview Unified Audit Log**.

You will:

1. Search the **Unified Audit Log** for Power Platform activity
2. Identify events generated from earlier labs (environment creation, DLP policy creation, etc.)
3. Export audit results
4. Analyze important fields used for **security monitoring and SIEM integration**

This lab demonstrates how enterprise security teams investigate Power Platform activity and integrate telemetry with SOC tools.

---

## Scenario

Your organization recently deployed governance controls across the Power Platform environment.

During the previous labs, administrators performed actions such as:

- Creating a **Power Platform environment**
- Creating **DLP policies**
- Assigning licenses and roles

Security operations teams must verify these activities using the **Unified Audit Log** in Microsoft Purview.

You have been asked to locate these events and analyze the audit record structure.

---

## Lab Environment

Students will use:

- Microsoft 365 Developer Tenant
- Microsoft Purview Compliance Portal
- Power Platform Admin Center (for reference)

---

## Required Permissions

To complete this lab the student account must have one of the following roles:

### Recommended

Compliance Administrator

### Alternative Roles

| Role | Capability |
| ----- | ----- |
| Global Administrator | Full access |
| Audit Reader | View audit logs only |
| Compliance Administrator | Full audit search capability |

Most Microsoft 365 Developer Tenants provide the default admin user with **Global Administrator**, which is sufficient.

---

## Concepts Covered

### Unified Audit Log

The **Unified Audit Log** collects events from Microsoft 365 services including:

- Exchange
- SharePoint
- Teams
- Power Platform
- Microsoft Entra ID

Power Platform events appear in the audit log when administrators perform actions such as:

- Creating environments
- Updating DLP policies
- Creating apps and flows
- Updating connectors

These events are critical for:

- Governance auditing
- Security monitoring
- SIEM integration

---

## Task 1 — Open Microsoft Purview

1. Navigate to the Microsoft Purview portal:

    <https://purview.microsoft.com>

2. Sign in using your administrator account.

---

## Task 2 — Open the Audit Search Tool

1. In the left navigation pane select: **Solutions → Audit**

2. Select **Audit Search**.

If prompted to enable auditing, select: **Start recording user and admin activity**

Most developer tenants already have auditing enabled.

---

## Task 3 — Configure an Audit Search

1. Click **New search**.

Configure the search with the following settings:

| Setting | Value |
| --- | --- |
| Date range | Last 7 days |
| Activities | Power Platform activities |
| Users | Leave blank |
| File, folder, or site | Leave blank |

Click **Search**.

---

## Task 4 — Identify Power Platform Events

Review the returned results.

Examples of events you may see from previous labs:

| Event Example | Description |
| --- | --- |
| PowerAppsEnvironmentCreated | Environment created |
| PowerAppsDlpPolicyCreated | DLP policy created |
| PowerAppsConnectorUpdated | Connector classification updated |
| PowerAutomateFlowCreated | Flow created |

Select one of the events to open the **details pane**.

---

## Task 5 — Review Key Audit Fields

Examine the event record.

Identify the following important fields:

| Field | Description |
| --- | --- |
| CreationTime | When the event occurred |
| UserId | User performing the action |
| Operation | Type of activity |
| Workload | Service generating the event |
| ClientIP | Source IP address |

These fields are commonly used in **SIEM monitoring rules**.

---

## Task 6 — Export Audit Results

1. Return to the audit search results page.

2. Select **Export**.

3. Save the file locally.

---

## Task 7 — Analyze the Exported Data

Open the CSV file using:

- Excel
- Google Sheets
- Any spreadsheet tool

Review the dataset and locate the following columns:

| Column | Purpose |
| --- | --- |
| CreationTime | Timestamp of activity |
| UserId | Identity performing action |
| Operation | Activity type |
| Workload | Microsoft service |
| AuditData | JSON payload with event details |

The **AuditData column** contains a JSON object with detailed metadata.

Security teams commonly parse this field when sending logs to a **SIEM platform**.

---

## Task 8 — Identify Monitoring Signals

Review the exported data and answer the following:

1. Which events correspond to the **DLP policy created earlier**?
2. Which events correspond to **environment creation**?
3. What user account performed those actions?
4. What timestamp was recorded?

---

## Task 9 — Consider SIEM Integration

Security teams often send the Unified Audit Log to SIEM systems such as:

- Microsoft Sentinel
- Splunk
- QRadar

These integrations use:

- Office 365 Management Activity API
- Purview Audit export

Discuss with your group:

Which fields would be most important for detecting suspicious activity?

Examples:

- Unusual connector creation
- Environment creation outside business hours
- High volume of flow creation

---

## Reflection Questions

1. Why is the Unified Audit Log important for Power Platform governance?
2. Which event fields would be useful for building SIEM alerts?
3. What risks exist if audit logs are not retained long enough?
4. What types of Power Platform activity should security teams monitor most closely?

---

## Key Takeaways

After completing this lab you should understand:

- How to search the Unified Audit Log
- How Power Platform events appear in Purview
- How audit records support governance and compliance
- How exported audit logs support **SIEM monitoring and security analytics**

Unified audit telemetry is a foundational component of **enterprise governance for Copilot and Power Platform environments**.
