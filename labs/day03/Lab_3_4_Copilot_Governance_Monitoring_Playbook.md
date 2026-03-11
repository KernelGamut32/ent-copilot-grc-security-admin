
# Lab 3.4 — Copilot Governance Monitoring Playbook (Capstone Lab)

## Course

Enterprise Copilot Governance, Security, and Administration

## Lab Duration

~60 minutes

## Lab Type

Capstone Governance Design + Validation

---

## Lab Objective

In this capstone lab you will design a **Copilot Governance Monitoring Playbook** for an enterprise Microsoft 365 environment.

You will:

1. Identify **monitoring signals for Copilot usage**
2. Map signals to **log sources available in Microsoft 365**
3. Define **alert conditions for risky activity**
4. Identify **containment and response actions**
5. Validate that the required telemetry exists in the tenant

This exercise brings together the governance controls implemented during the course.

---

## Scenario

Your organization has completed a **Copilot readiness assessment** and plans to expand Copilot usage to additional departments.

Before rollout, security leadership requires a **monitoring and incident response playbook** to detect:

• Data exposure risks  
• Oversharing activity  
• Suspicious automation activity  
• Sensitive file access patterns  

You have been asked to design a **Copilot Monitoring Playbook** and confirm that the required telemetry exists in the tenant.

---

## Lab Environment

Students will use the same **Microsoft 365 Developer Tenant** used throughout the course.

Tools used in this lab:

• Microsoft Purview  
• Microsoft Entra Admin Center  
• Power Platform Admin Center  
• SharePoint Admin Center

---

## Required Permissions

Recommended role: **Global Administrator**

Alternative roles (combined):

| Role | Purpose |
| ----- | ----- |
| Compliance Administrator | Audit log and Purview investigation |
| Power Platform Administrator | Flow monitoring |
| SharePoint Administrator | Data access monitoring |
| Security Administrator | Identity and session monitoring |

---

## Important Developer Tenant Note

Microsoft 365 Developer Tenants typically **do not include Microsoft 365 Copilot**.

Therefore:

• Copilot telemetry may not exist yet

However, the **same telemetry sources Copilot relies on** can still be validated:

• Purview Unified Audit Log  
• SharePoint access events  
• Power Automate activity  
• Entra sign-in logs

These signals are the foundation of **Copilot monitoring programs**.

---

## Task 1 — Identify Monitoring Signals

Review the following potential monitoring signals for Copilot environments.

| Risk Scenario | Monitoring Signal |
| --- | --- |
| Large data access spikes | File access activity |
| Sensitive data exposure | DLP rule match |
| Overshared content | SharePoint sharing changes |
| Automation exfiltration | HTTP connector usage |
| Account compromise | Unusual sign-in activity |

Select the **top five signals** your organization should monitor.

---

## Task 2 — Map Signals to Log Sources

For each monitoring signal identify the Microsoft 365 log source.

| Signal | Log Source |
| --- | --- |
| File access activity | |
| DLP rule matches | |
| Power Automate flow runs | |
| SharePoint sharing changes | |
| Sign-in anomalies | |

Use the following portals to verify logs exist:

• <https://purview.microsoft.com>  
• <https://entra.microsoft.com>  
• <https://admin.powerplatform.microsoft.com>

---

## Task 3 — Verify Audit Telemetry Exists

Navigate to:

<https://purview.microsoft.com>

Open: **Solutions → Audit → Search**

Run a search for:

| Setting | Value |
| --- | --- |
| Date range | Last 7 days |
| Activities | All activities |

Confirm that the tenant is collecting:

• SharePoint file activity  
• Power Automate activity  
• DLP events

Export a sample dataset.

---

## Task 4 — Verify SharePoint Governance Signals

Navigate to:

<https://admin.microsoft.com/sharepoint>

Open: **Sites → Active Sites**

Review site sharing settings.

Identify whether any sites allow:

• Everyone except external users  
• External sharing

These represent potential **Copilot grounding exposure risks**.

---

## Task 5 — Review Power Automate Activity

Navigate to:

<https://admin.powerplatform.microsoft.com>

Open: **Environments → Default → Resources → Flows**

Check flows for:

• HTTP connector usage  
• External API calls  
• High run frequency

Document findings.

---

## Task 6 — Review Identity Monitoring Signals

Navigate to:

<https://entra.microsoft.com>

Open: **Monitoring → Sign-in logs**

Review recent sign-ins for:

• unusual locations  
• high frequency activity  
• failed sign-in attempts

These signals may indicate compromised accounts.

---

## Task 7 — Design Alert Rules

Based on your monitoring signals, define alert rules.

| Alert Name | Trigger Condition | Log Source |
| --- | --- | --- |
| | | |
| | | |
| | | |

Example alerts:

• High-volume file access by one user  
• DLP override events  
• Flow sending data externally

---

## Task 8 — Define Response Playbook

For each alert define response actions.

| Alert | Investigation Action | Containment Action |
| --- | --- | --- |
| | | |
| | | |
| | | |

Example actions:

• Review audit logs  
• Disable automation flows  
• Revoke user sessions

---

## Task 9 — Create Copilot Monitoring Playbook

Document your final monitoring playbook.

## Copilot Governance Monitoring Plan

| Area | Monitoring Approach |
| --- | --- |
| Data access monitoring | |
| Automation monitoring | |
| Identity monitoring | |
| Data protection monitoring | |

---

## Task 10 — Present Your Governance Plan

Prepare a short summary for the class.

Your plan should explain:

• Key monitoring signals  
• Log sources used  
• Alert conditions  
• Incident response steps

---

## Reflection Questions

1. Why is telemetry important for governing AI tools like Copilot?
2. Which signals would indicate potential data exfiltration?
3. How could Sentinel or SIEM integration improve monitoring?
4. What governance gaps did you identify in the lab tenant?

---

## Key Takeaways

After completing this lab you should understand:

• How organizations monitor Copilot usage  
• Which Microsoft 365 telemetry sources support AI governance  
• How to design detection rules for data exposure risks  
• How monitoring integrates with incident response processes

A strong monitoring playbook is essential for **safe enterprise deployment of Microsoft 365 Copilot**.
