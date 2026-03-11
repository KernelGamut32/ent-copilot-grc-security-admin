
# Lab 3.2 — DSPM for AI Posture Review (Purview Governance Simulation)

## Course

Enterprise Copilot Governance, Security, and Administration

## Lab Duration

~60 minutes

## Lab Objective

In this lab you will perform a **Data Security Posture Management (DSPM) for AI–style review** using Microsoft Purview tools available in a Microsoft 365 Developer Tenant.

You will:

1. Review the **AI governance posture concept** used in DSPM for AI
2. Use Microsoft Purview dashboards to identify **potential data exposure risks**
3. Identify the **top three security posture findings**
4. Document recommended remediation actions
5. Simulate remediation by **restricting a SharePoint site's sharing settings**
6. Verify that the configuration change is reflected in the tenant’s governance posture

---

## Lab Scenario

Your organization is preparing to expand its Microsoft 365 Copilot deployment.

The security team must perform a **DSPM for AI posture review** to ensure sensitive data is not exposed through Copilot grounding.

The posture review focuses on:

• Overshared SharePoint sites  
• Unlabeled sensitive files  
• Broad access permissions

You will investigate these risks and simulate remediation actions.

---

## Lab Environment

Students will use:

• Microsoft 365 Developer Tenant  
• Microsoft Purview Compliance Portal  
• SharePoint Admin Center

---

## Required Permissions

Recommended role: **Compliance Administrator**

Additional roles that may be required:

| Role | Purpose |
| ----- | ----- |
| SharePoint Administrator | Modify site sharing settings |
| Global Administrator | Full administrative access |

---

## Concepts Covered

### DSPM for AI

Microsoft Purview **DSPM for AI** helps organizations:

• Identify AI‑exposed data risks  
• Detect overshared content used by Copilot grounding  
• Highlight sensitive data without protection  
• Recommend remediation actions

These insights help organizations maintain **secure AI deployments**.

---

### Task 1 — Open Microsoft Purview

1. Navigate to:

    <https://purview.microsoft.com>

2. Sign in with your administrator account.

---

### Task 2 — Review Security Posture Indicators

Navigate to: **Posture**

Review available posture indicators such as:

• Sensitive data discovered  
• Label coverage  
• File activity alerts

These indicators simulate the **DSPM posture summary**.

---

### Task 3 — Identify Potential High‑Severity Findings

Review the dashboard and identify **three potential governance risks**.

Examples may include:

| Finding | Risk |
| --- | --- |
| Files without sensitivity labels | Data classification gap |
| Sites shared broadly | Oversharing risk |
| External sharing enabled | Data exposure risk |

Document the **top three findings** you identify.

---

### Task 4 — Document Recommended Remediation

For each finding record a remediation action.

Example:

| Finding | Recommended Action |
| --- | --- |
| Unlabeled files | Apply sensitivity labels |
| Overshared SharePoint site | Restrict site permissions |
| External sharing enabled | Limit sharing to internal users |

---

### Task 5 — Simulate a Remediation Action

You will now simulate remediation by restricting SharePoint sharing.

1. Navigate to:

    <https://admin.microsoft.com/sharepoint>

2. Select: **Sites → Active sites**

3. Choose a site from the list.

4. Open: **Settings**

5. Review **More sharing settings**

---

### Task 6 — Restrict Site Sharing

Change the sharing setting to: **Only people in your organization**

Save the change.

This simulates **reducing AI exposure risk by limiting data sharing**.

---

### Task 7 — Verify the Governance Change

Return to the SharePoint Admin Center.

Review the site configuration to confirm:

| Setting | Expected Value |
| --- | --- |
| External sharing | Disabled or restricted |
| Site access | Internal users only |

Record confirmation of the remediation.

---

### Task 8 — Document Posture Review Results

Complete the table below.

| Finding | Severity | Remediation | Status |
| --- | --- | --- | --- |
| | | | |
| | | | |
| | | | |

---

### Task 9 — Create a Posture Review Summary

Prepare a short summary report.

### AI Security Posture Summary

| Field | Value |
| --- | --- |
| Tenant reviewed | |
| Review date | |
| Top risks identified | |
| Remediation actions taken | |

---

### Governance Recommendation

Describe whether the tenant is ready for **expanded Copilot deployment**.

---

## Reflection Questions

1. Why is DSPM important when deploying AI tools like Copilot?
2. What risks arise when SharePoint sites are overshared?
3. How can organizations automate posture monitoring?
4. Which governance controls reduce AI data exposure risk?

---

## Key Takeaways

After completing this lab you should understand:

• How DSPM for AI identifies data exposure risks  
• How administrators analyze AI governance posture  
• How oversharing increases Copilot grounding exposure  
• How remediation actions improve AI security posture

DSPM capabilities help organizations maintain **continuous governance for AI-enabled environments**.
