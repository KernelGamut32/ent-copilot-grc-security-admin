
# Lab 3.3 — Copilot Security Incident Response Tabletop

## Course

Enterprise Copilot Governance, Security, and Administration

## Lab Duration

~60 minutes

## Lab Type

Tabletop Investigation + Tenant Evidence Collection

---

## Lab Objective

In this lab you will participate in a **security incident response tabletop exercise** focused on Microsoft 365 Copilot and Power Platform activity.

You will:

1. Analyze a simulated **P1 security alert scenario**
2. Identify the **incident response command structure**
3. Determine **containment actions**
4. Collect and preserve **forensic evidence from Microsoft 365**
5. Assess whether the scenario represents a **reportable breach**
6. Document your response decisions

The exercise simulates how a **SOC and governance team respond to Copilot-related security events**.

---

## Scenario

A **Microsoft Sentinel alert** fires at **11:47 PM on Tuesday**.

The alert correlates:

* A **CopilotInteraction spike** (850 file access events in 90 minutes)  
* A **DLP override event** for a document labeled  
  **Highly Confidential – Financial**  

The activity originates from a **Senior Finance Analyst**.

Additional context:

* The analyst is currently **traveling to an approved location**.  
* A second alert shows a **Power Automate flow posting data to an unknown HTTP endpoint**.

Security operations must determine whether:

* This is legitimate business activity  
* A compromised account  
* A data exfiltration attempt  

---

## Lab Environment

Students will investigate using:

* Microsoft Purview  
* Microsoft Entra Admin Center  
* Power Platform Admin Center  
* SharePoint Admin Center  

---

## Required Permissions

Recommended role: **Global Administrator**

Alternative roles (combined):

| Role | Purpose |
| ----- | ----- |
| Compliance Administrator | Audit log investigation |
| Power Platform Administrator | Flow investigation |
| SharePoint Administrator | Data access review |
| Security Administrator | Incident containment |

---

## Important Tenant Limitation

Developer tenants **normally do not include Microsoft 365 Copilot**.

Therefore:

* **CopilotInteraction events may not exist**

Students will still perform the **investigation workflow using available audit events**.

This mirrors real SOC investigation processes.

---

## Task 1 — Identify the Incident Response Team

Based on the scenario, identify the **incident response leadership structure**.

Document:

| Role | Responsible Team |
| --- | --- |
| Incident Commander | |
| Security Operations Lead | |
| Power Platform Administrator | |
| Data Protection Officer | |
| Legal / Compliance | |

---

## Task 2 — Verify Privileged Access Availability

The alert occurred **after hours (11:47 PM)**.

Check whether administrators could activate roles using **PIM**.

Navigate to:

  <https://entra.microsoft.com>

Open: **Identity Governance → Privileged Identity Management → Roles**

Verify if **Power Platform Administrator** role supports **eligible activation**.

Record findings.

---

## Task 3 — Investigate Audit Logs

Navigate to:

  <https://purview.microsoft.com>

Open: **Solutions → Audit → Search**

Run a search:

| Setting | Value |
| --- | --- |
| Date range | Last 7 days |
| User | Finance analyst account |
| Activities | All activities |

Export results.

Look for:

* File access activity  
* Power Automate activity  
* DLP rule events

---

## Task 4 — Investigate DLP Events

In Purview Audit search run a second query:

| Setting | Value |
| --- | --- |
| Activity | DLPRuleMatch |
| User | Same user |
| Date range | Last 7 days |

Document findings.

| Field | Value |
| --- | --- |
| Rule triggered | |
| File name | |
| Location | |

---

## Task 5 — Investigate Power Automate Activity

Navigate to:

<https://admin.powerplatform.microsoft.com>

Open: **Environments → Default → Resources → Flows**

Review flows owned by the user.

Check for:

* HTTP connector usage  
* Recent runs  
* External endpoints

Document findings.

---

## Task 6 — Evidence Preservation

Before containment actions occur, identify evidence that must be preserved.

Possible evidence sources:

| Evidence Source | Export Method |
| --- | --- |
| Purview Audit Logs | CSV export |
| Power Automate run history | Export flow run data |
| SharePoint access logs | Audit search |
| Entra sign-in logs | Export logs |

Document what must be collected.

---

## Task 7 — Containment Strategy

Based on the scenario, rank the following containment actions.

| Containment Action | Priority |
| --- | --- |
| Suspend Copilot access | |
| Disable Power Automate flow | |
| Revoke user session tokens | |
| Reset user credentials | |

Explain why you chose this order.

---

## Task 8 — Simulate Containment

Perform one simulated containment action.

Example:

### Revoke User Sessions

Navigate to:

  <https://entra.microsoft.com>

Open: **Users → Select user → Sign-in logs**

Select: **Revoke sessions**

Confirm the action.

---

## Task 9 — Breach Notification Assessment

Evaluate whether this scenario may require regulatory notification.

Consider:

| Regulation | Consideration |
| --- | --- |
| GDPR | Exposure of personal data |
| HIPAA | Exposure of protected health information |
| Financial regulations | Access to financial reports |

Document your assessment.

---

## Task 10 — Incident Summary Report

Prepare a short investigation summary.

### Incident Summary

| Field | Value |
| --- | --- |
| Incident type | |
| User investigated | |
| Data accessed | |
| Potential risk | |

---

### Evidence Collected

List exported logs and data sources.

---

### Containment Actions Taken

Document actions executed.

---

### Final Determination

| Outcome | Decision |
| --- | --- |
| Security incident confirmed | Yes / No |
| Data breach likely | Yes / No |

---

## Reflection Questions

1. What signals suggested possible data exfiltration?
2. What additional telemetry would help confirm the incident?
3. How could Sentinel automation accelerate this response?
4. What governance controls could prevent similar incidents?

---

## Key Takeaways

After completing this lab you should understand:

* How SOC teams investigate Copilot-related alerts  
* How to correlate audit, DLP, and automation telemetry  
* How to preserve evidence before containment  
* How to determine regulatory breach obligations  

Incident response readiness is a critical component of **enterprise Copilot governance**.
