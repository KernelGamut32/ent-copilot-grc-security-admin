# Lab 1.1 — Tenant Readiness Assessment

## Course

Enterprise Copilot Governance, Security, and Administration

## Lab Objective

In this lab, you will perform a **Microsoft 365 tenant readiness assessment** aligned with Copilot governance baseline practices. You will validate key configuration areas in a Microsoft 365 Developer Tenant and document findings.

You will verify:

- Microsoft Purview Audit Log status
- Microsoft 365 Apps update channel configuration
- Conditional Access policies or Security Defaults
- MFA and identity baseline posture

The goal is to determine whether the tenant meets baseline **Copilot readiness and governance requirements**.

---

## Lab Scenario

Your organization is preparing to enable **Microsoft 365 Copilot and Copilot Studio** across the enterprise.

Before rollout, the governance team must perform a **tenant readiness assessment** to verify that core security, compliance, and identity controls are configured.

You have been asked to review the environment and document whether the tenant meets the baseline governance requirements.

---

### Estimated Time

30–40 minutes

---

### Lab Environment

Students will perform this lab using:

- **Microsoft 365 Developer Tenant**
- Web browser

---

### Required Permissions

To complete this lab, the student account must have one of the following:

### Recommended Role

Global Administrator

### Alternative Roles

These combinations also work:

| Task | Required Role |
| ----- | ----- |
| View audit log configuration | Compliance Administrator or Global Admin |
| View Conditional Access policies | Security Administrator or Global Admin |
| View Microsoft 365 Apps settings | Global Admin |

In most Microsoft 365 Developer Tenants, the **default user account is already a Global Administrator**, which is sufficient for the lab.

---

### Baseline Requirements for Copilot Readiness

During the lab you will validate the tenant against the following baseline:

| Control Area | Baseline Requirement |
| --- | --- |
| Audit Logging | Microsoft Purview audit logging enabled |
| Identity Security | MFA enforced via Security Defaults or Conditional Access |
| Conditional Access | Policies exist to protect Microsoft 365 access |
| Microsoft 365 Apps | Current Channel or Monthly Enterprise Channel |
| Tenant Monitoring | Audit logs accessible for investigation |

---

### Lab Tasks

#### Task 1 — Verify Microsoft Purview Audit Logging

Microsoft 365 Copilot activity is logged in **Microsoft Purview Audit**. Audit logging must be enabled for governance and investigations.

##### Step 1

Open the **Microsoft Purview portal**

<https://purview.microsoft.com>

Sign in using your administrator account.

---

##### Step 2

In the left navigation panel select: **Solutions → Audit**

If audit logging is not enabled, you will see a message asking you to start recording activity.

---

##### Step 3

Verify audit logging status.

You should see the **Audit search interface**.

If the message **"Start recording user and admin activity"** appears, click the button to enable it.

---

#### Task 2 — Review Audit Log Retention Tier

Audit retention depends on Microsoft 365 licensing.

##### Step 1

In the **Purview Audit page**, select: **Audit search**

---

##### Step 2

Run a simple search:

Activity:
Select a couple of events

Date range:
Last 24 hours

Click **Search**.

---

##### Step 3

Explore any events that are returned.

Record:

- Number of events returned
- Example activity type

This confirms that **audit telemetry is operational**.

---

#### Task 3 — Review Conditional Access Policies

Copilot access relies on Microsoft Entra ID identity controls.

##### Step 1

Open the **Microsoft Entra Admin Center**

<https://entra.microsoft.com>

---

##### Step 2

Navigate to: **Conditional Access**

---

##### Step 3

Review existing policies.

Possible outcomes in a Developer Tenant:

| Scenario | Meaning |
| --- | --- |
| Policies exist | Conditional Access is configured |
| No policies exist | Tenant may rely on Security Defaults |

---

##### Step 4

Record:

- Number of Conditional Access policies
- Example policy name
- Targeted users or groups

---

#### Task 4 — Check Security Defaults

If Conditional Access policies are not configured, Microsoft may enable **Security Defaults**.

##### Step 1

In the **Entra Admin Center**, navigate to: **Overview**

---

##### Step 2

Select: **Properties**

---

##### Step 3

Scroll to the bottom and locate: **Security Defaults**

Click **Manage security defaults**.

---

##### Step 4

Verify whether Security Defaults are:

- Enabled
- Disabled

Record the result.

Security Defaults enforce:

- MFA registration
- MFA for admins
- Basic identity protections

---

#### Task 5 — Review Microsoft 365 Apps Update Channel

Microsoft 365 Copilot requires **supported update channels** for Office applications.

Even if no devices are enrolled in a Developer Tenant, you can verify the configured channel policies.

---

##### Step 1

Open the **Microsoft 365 Apps Admin Center**

<https://config.office.com>

---

##### Step 2

Navigate to: **Inventory → Devices**

Developer tenants may show **no devices**, which is normal.

---

##### Step 3

Navigate to: **Customization → Policy Management**

Check for any Office update policies.

---

##### Step 4

Record:

- Are update policies configured?
- Which update channel is specified?

Typical acceptable channels:

- Current Channel
- Monthly Enterprise Channel

---

#### Task 6 — Document Findings

Create a readiness report using the template below.

---

##### Tenant Readiness Report Template

Tenant Name:

Date:

Administrator:

| Area | Requirement | Status | Notes |
| --- | --- | --- | --- |
| Audit Logging | Enabled in Purview | | |
| Conditional Access | Policies configured or Security Defaults enabled | | |
| MFA Baseline | MFA enforced | | |
| Audit Telemetry | Events visible in audit search | | |
| Office Update Channel | Supported update channel configured | | |

---

## Reflection Questions

Answer the following:

1. Why is audit logging critical for Copilot governance?
2. What risks exist if Conditional Access policies are not configured?
3. Why does Microsoft recommend Current Channel or Monthly Enterprise Channel for Copilot?
4. What additional controls would you implement before enabling Copilot enterprise-wide?

---

## Key Takeaways

After completing this lab you should understand:

- How to validate a tenant's governance readiness
- How to confirm audit telemetry is operational
- How identity controls influence Copilot security
- How to document governance readiness findings

This readiness assessment is typically performed **before any Copilot rollout** in enterprise environments.
