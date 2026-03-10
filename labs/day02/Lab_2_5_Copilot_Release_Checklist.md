
# Lab 2.5 — Copilot Release Checklist and Approval Record

## Course

Enterprise Copilot Governance, Security, and Administration

## Lab Duration

~60 minutes

## Lab Objective

In this lab you will complete a **simulated pre-release governance review** for enabling Microsoft 365 Copilot in an enterprise tenant.

You will:

1. Review Copilot readiness requirements
2. Collect **evidence artifacts** from the tenant configuration
3. Complete a **release readiness checklist**
4. Prepare a **mock approval record**
5. Submit the documentation to the lab facilitator

This lab reinforces the **governance review process required before enabling Copilot in production environments**.

> NOTE: Microsoft 365 Developer Tenants typically **do not include Microsoft 365 Copilot licenses**.  
> This lab focuses on the **governance review process**, not enabling the Copilot service itself.

---

## Lab Scenario

Your organization is preparing to enable **Microsoft 365 Copilot** for a pilot group.

Before rollout, the security and governance team requires a **pre-release security review**.

The review validates that:

- Identity controls are in place
- Data protection policies are configured
- Power Platform governance policies are implemented
- Oversharing risks are reviewed

You have been asked to complete the **Copilot Release Checklist** and submit an approval package.

---

## Lab Environment

Students will use the same **Microsoft 365 Developer Tenant** used in previous labs.

You may reference evidence from:

- Microsoft Entra Admin Center
- Microsoft Purview portal
- Power Platform Admin Center
- SharePoint Admin Center

---

## Required Permissions

Recommended role: **Global Administrator**

Alternative roles (combined):

| Role | Purpose |
| ----- | ----- |
| Compliance Administrator | Purview policies and audit |
| Power Platform Administrator | DLP policy verification |
| SharePoint Administrator | Oversharing review |
| Security Administrator | Identity policy verification |

---

### Governance Controls Reviewed

Your review will validate the following controls implemented during earlier labs.

| Governance Area | Example Evidence |
| --- | --- |
| Identity governance | PIM configuration |
| Data protection | Sensitivity labels |
| Power Platform governance | DLP policies |
| Data exposure risk | Oversharing analysis |
| Audit monitoring | Purview audit logs |

These controls align with enterprise Copilot governance guidance.

---

### Task 1 — Review Identity Governance

Navigate to:

    <https://entra.microsoft.com>

Open: **Identity Governance → Privileged Identity Management**

Confirm the following:

| Control | Expected Status |
| --- | --- |
| PIM enabled for admin roles | Yes |
| Power Platform Administrator eligible role | Configured |
| Role activation requires MFA | Enabled |

Record your findings.

---

### Task 2 — Verify Data Protection Controls

Navigate to:

    <https://purview.microsoft.com>

Open: **Information Protection → Sensitivity labels**

Confirm the presence of: **Confidential – Internal Only**

Verify:

- Encryption enabled
- Label policy published

Record evidence.

---

### Task 3 — Verify Power Platform Governance

Navigate to:

<https://admin.powerplatform.microsoft.com>

Open: **Policies → Data policies**

Confirm the presence of the DLP policy created in previous labs.

Verify:

| Setting | Expected Value |
| --- | --- |
| Policy name | Copilot-Governance-DLP |
| Scope | All environments |
| Blocked connector | HTTP |
| Business connectors | SharePoint, Teams, Dataverse |

Record results.

---

### Task 4 — Review SharePoint Oversharing Risk

Navigate to:

<https://admin.microsoft.com/sharepoint>

Open: **Sites → Active sites**

Review permissions for at least **three SharePoint sites**.

Check for the presence of: **Everyone except external users**

Record potential oversharing risks.

---

### Task 5 — Review Audit Logging

Navigate to:

<https://purview.microsoft.com>

Open: **Solutions → Audit**

Run a search for:

- Power Platform activity
- SharePoint activity

Confirm audit events exist.

Record sample events.

---

### Task 6 — Collect Evidence Artifacts

Capture the following evidence:

| Artifact | Source |
| --- | --- |
| PIM configuration screenshot | Entra portal |
| Sensitivity label configuration | Purview portal |
| DLP policy configuration | Power Platform admin center |
| SharePoint permissions review | SharePoint admin center |
| Audit log event example | Purview audit search |

Save evidence for submission.

---

### Task 7 — Complete the Copilot Release Checklist

Use the checklist below.

| Control | Status | Evidence |
| --- | --- | --- |
| PIM configured for admin roles | | |
| Sensitivity labels deployed | | |
| Power Platform DLP policy active | | |
| Oversharing review completed | | |
| Audit logging enabled | | |

---

### Task 8 — Create the Approval Record

Complete the approval form below.

#### Copilot Pre‑Release Approval Record

| Field | Value |
| --- | --- |
| Tenant name | |
| Review date | |
| Reviewer | |
| Copilot rollout scope | Pilot group |
| Security review completed | Yes / No |

#### Findings Summary

Describe any risks discovered during the review.

#### Remediation Plan

Document actions required before rollout.

#### Approval Decision

| Decision | Value |
| --- | --- |
| Approved for pilot rollout | Yes / No |
| Conditions | |

---

### Task 9 — Submit the Approval Package

Provide the following to the lab facilitator:

1. Completed **release checklist**
2. **Approval record**
3. Evidence artifacts

The facilitator will review the package and confirm whether Copilot deployment would be approved.

---

## Reflection Questions

1. Why is a governance checklist required before enabling Copilot?
2. Which control area is most important for preventing data exposure?
3. How could organizations automate governance reviews?
4. What additional controls might be required in regulated industries?

---

## Key Takeaways

After completing this lab you should understand:

- How enterprises perform Copilot readiness reviews
- How governance evidence is collected across Microsoft 365 services
- How security teams approve AI feature deployment
- How governance processes support safe Copilot adoption

A structured release approval process ensures **AI capabilities are deployed responsibly and securely**.
