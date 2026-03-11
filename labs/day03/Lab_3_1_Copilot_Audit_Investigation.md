
# Lab 3.1 — Copilot Audit Investigation

## Course

Enterprise Copilot Governance, Security, and Administration

## Lab Duration

~60 minutes

## Lab Objective

In this lab you will conduct a **security investigation using Microsoft Purview Audit logs** related to Microsoft Copilot activity.

You will:

1. Search the **Unified Audit Log** for Copilot-related activity for a specific user.
2. Export audit results to CSV.
3. Identify **files referenced as grounding sources** in Copilot interactions.
4. Cross-reference the same user activity with **DLP rule match events**.
5. Determine whether any accessed files **lack sensitivity labels**.
6. Produce a short **incident scope report** summarizing your findings.

> NOTE: Many Microsoft 365 Developer Tenants do **not include Microsoft 365 Copilot licenses**, meaning `CopilotInteraction` events may not exist in the tenant.  
> If no Copilot events are returned, you will still perform the investigation process using the available audit logs to understand how the investigation workflow works.

---

## Lab Scenario

A security analyst receives a report that a user may have accessed sensitive information through Microsoft Copilot.

The investigation must determine:

- What Copilot prompts were issued
- Which files were used as **grounding sources**
- Whether any **DLP policy matches occurred**
- Whether any accessed files were **missing sensitivity labels**

You will investigate the activity using the **Microsoft Purview Unified Audit Log**.

---

## Lab Environment

Students will use:

- Microsoft 365 Developer Tenant
- Microsoft Purview Compliance Portal
- Microsoft Excel or another spreadsheet tool

---

## Required Permissions

Recommended role: **Compliance Administrator**

Alternative roles:

| Role | Capability |
| ----- | ----- |
| Global Administrator | Full access |
| Audit Reader | View audit log events |

These roles allow:

- Searching the Unified Audit Log
- Exporting audit results
- Reviewing activity data

---

## Concepts Covered

### Copilot Audit Events

When Microsoft 365 Copilot is enabled, audit logs may include events such as:

| Event | Description |
| ------ | ------------- |
| CopilotInteraction | User prompt and Copilot response event |
| CopilotGroundingContentAccessed | Files used to generate Copilot responses |
| DLPRuleMatch | DLP policy triggered on content access |

These events help investigators determine **what data Copilot used and whether policy violations occurred**.

---

### Task 1 — Open Microsoft Purview

1. Navigate to:

    <https://purview.microsoft.com>

2. Sign in with your administrator account.

---

### Task 2 — Open the Audit Search Tool

1. Select: **Solutions → Audit**

2. Choose **Search**.

Confirm auditing is enabled.

If not enabled, select:

**Start recording user and admin activity**.

---

### Task 3 — Search for Copilot Interaction Events

Create a new search.

| Setting | Value |
| --- | --- |
| Activity | Interacted with Copilot |
| Date range | Last 7 days |
| Users | Select a specific lab user |
| Workload | Microsoft Copilot |

Run the search.

---

#### Possible Results

| Result | Meaning |
| ------ | ------ |
| Events returned | Copilot activity occurred |
| No results | Tenant does not currently have Copilot events |

Record the outcome.

---

### Task 4 — Export the Results

If events exist:

1. Select **Export → Download all results**.
2. Choose **CSV format**.
3. Save the file locally.

If no events exist, proceed with the lab by exporting **any available audit events** for the same user to practice the investigation workflow.

---

### Task 5 — Identify Grounding Content

Open the exported CSV file.

Locate the column: **AuditData**

This field contains a JSON object with detailed activity data.

Search for fields such as:

- `SourceFileName`
- `SourceFileExtension`
- `SiteUrl`
- `ItemId`

These indicate **files accessed to generate responses**.

Document any files referenced.

---

### Task 6 — Cross-Reference DLP Rule Matches

Return to the **Audit Search page**.

Run another search.

| Setting | Value |
| --- | --- |
| Activity | Matched DLP rule |
| Date range | Last 7 days |
| User | Same user as earlier |

Run the search.

---

### Task 7 — Review DLP Results

Examine returned events.

If events exist, review:

| Field | Meaning |
| --- | --- |
| RuleName | DLP policy triggered |
| SensitiveInfoType | Data type detected |
| Location | File or service location |

Export the results if needed.

---

### Task 8 — Determine Label Status

Navigate to the SharePoint site containing the identified files.

Open the document library.

Check whether files have a **Sensitivity Label** applied.

Document:

| File Name | Label Applied | Location |
| --- | --- | --- |
| | | |
| | | |

Files without labels may represent governance risk.

---

### Task 9 — Create an Incident Scope Report

Prepare a short investigation report.

#### Incident Scope Summary

| Field | Value |
| --- | --- |
| User investigated | |
| Time window | Last 7 days |
| Copilot interaction events found | |
| Grounding files identified | |
| DLP events detected | |

---

#### Risk Assessment

Describe whether sensitive or unlabeled files were accessed.

---

#### Recommended Actions

Examples:

- Apply sensitivity labels
- Restrict SharePoint access
- Review DLP policy coverage
- Monitor future Copilot activity

---

## Reflection Questions

1. Why is audit telemetry important for Copilot investigations?
2. What types of data exposure could occur through Copilot grounding?
3. How can organizations automate Copilot monitoring?
4. Which fields are most important for SIEM correlation?

---

## Key Takeaways

After completing this lab you should understand:

- How Copilot activity appears in the Microsoft Purview audit log
- How investigators trace Copilot interactions to source files
- How DLP and labeling data affect Copilot governance
- How audit exports support security incident investigations

Audit telemetry is essential for **monitoring and investigating AI-assisted activity in Microsoft 365 environments**.
