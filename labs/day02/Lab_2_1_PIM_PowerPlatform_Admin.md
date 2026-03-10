
# Lab 2.1 — Configure Privileged Identity Management (PIM) for Power Platform Administrator

## Course

Enterprise Copilot Governance, Security, and Administration

## Lab Duration

~60 minutes

## Lab Objective

In this lab you will configure **Microsoft Entra Privileged Identity Management (PIM)** to control administrative access to the **Power Platform Administrator** role.

You will:

1. Assign the **Power Platform Administrator** role as an **eligible** assignment (not permanent)
2. Configure an **activation policy** requiring:
   - Multi‑Factor Authentication (MFA)
   - Approval
3. Activate the role through the **PIM portal**
4. Verify the **role activation event in Microsoft Entra audit logs**

This lab demonstrates how organizations implement **Just‑In‑Time (JIT) privileged access** for Power Platform administration.

---

## Scenario

Your organization wants to reduce risk associated with **permanent administrative privileges**.

Instead of assigning permanent roles, administrators must:

- Request privileged access when needed
- Activate roles for a limited duration
- Have actions recorded in audit logs

The security team has decided that **Power Platform Administrator** access will be managed through **Microsoft Entra Privileged Identity Management (PIM)**.

You have been asked to configure the role and validate the activation process.

---

## Lab Environment

Students will use:

- Microsoft 365 Developer Tenant
- Microsoft Entra Admin Center
- Microsoft Entra Privileged Identity Management
- Microsoft Entra Audit Logs

> Microsoft 365 Developer tenants with **Microsoft 365 E5 Developer** include **Microsoft Entra ID P2**, which enables Privileged Identity Management.

---

## Required Permissions

To complete this lab the student account must have one of the following roles:

### Recommended

Global Administrator

### Alternative

Privileged Role Administrator

These roles allow:

- Managing Microsoft Entra roles
- Configuring Privileged Identity Management
- Viewing Entra audit logs

---

## Concepts Covered

### Privileged Identity Management

Microsoft Entra **Privileged Identity Management (PIM)** allows organizations to:

- Provide **Just‑In‑Time administrative access**
- Require **approval and MFA**
- Enforce **time‑limited access**
- Audit privileged activity

Instead of permanent access:

```menu
User → Eligible Role → Activation Request → Temporary Admin Access
```

---

#### Task 1 — Open Microsoft Entra Privileged Identity Management

1. Navigate to the **Microsoft Entra Admin Center**

   <https://entra.microsoft.com>

2. In the left navigation pane select: **Identity Governance → Privileged Identity Management**

3. Select: **Microsoft Entra roles**

---

#### Task 2 — Locate the Power Platform Administrator Role

1. Select **Roles**.

2. In the role list search for: **Power Platform Administrator**

3. Select the role.

You will now see the role overview including:

- Eligible assignments
- Active assignments
- Role settings

---

#### Task 3 — Assign an Eligible Role

1. Select **Assignments → Add assignments**.

2. Configure the assignment:

   | Setting | Value |
   | --- | --- |
   | Assignment type | Eligible |
   | Member | Select your user account |
   | Start time | Now |
   | End time | No expiration |

3. Click **Assign**.

The role is now **eligible but not active**.

---

#### Task 4 — Configure the Role Activation Policy

Next you will configure security controls for role activation.

1. In the **Power Platform Administrator role**, select: **Settings**

2. Select **Activation settings**.

Configure the following:

| Setting | Value |
| --- | --- |
| Require MFA on activation | Enabled |
| Require approval to activate | Enabled |
| Maximum activation duration | 4 hours |
| Require justification | Enabled |

---

#### Configure Approvers

Under **Approvers**, add:

- The administrator account

Click **Save**.

---

#### Task 5 — Request Role Activation

Now simulate an administrator requesting access.

1. Navigate to: **Privileged Identity Management → My roles**

2. Under **Eligible assignments**, locate: **Power Platform Administrator**

3. Select **Activate**.

---

### Configure Activation Request

Fill in the activation form.

| Field | Value |
| --- | --- |
| Reason | Power Platform governance lab |
| Duration | 1 hour |

Submit the request.

---

#### Task 6 — Approve the Request

If approval is required, the approver must approve the request.

Approver steps:

1. Navigate to: **Privileged Identity Management → Approvals**

2. Select the pending request.

3. Click **Approve**.

After approval, the role becomes **active for the requested duration**.

---

#### Task 7 — Verify Active Role

1. Navigate to: **Privileged Identity Management → My roles**

2. Under **Active assignments**, confirm:

**Power Platform Administrator** is active.

You now have temporary administrative privileges.

---

#### Task 8 — Verify the Activation Event in Entra Logs

1. In the Microsoft Entra Admin Center navigate to: **Monitoring → Audit logs**

2. Configure the filter:

   | Setting | Value |
   | --- | --- |
   | Activity | Add member to role OR Activate eligible role |
   | Time range | Last 1 hour |

3. Review the event details.

---

#### Task 9 — Examine Important Audit Fields

Open the activation event and identify:

| Field | Description |
| --- | --- |
| Activity | Role activation |
| InitiatedBy | User requesting access |
| TargetResources | Role activated |
| Result | Success or failure |
| TimeGenerated | Timestamp |

These fields are commonly used for:

- SOC monitoring
- SIEM alerting
- Compliance audits

---

#### Task 10 — Document Results

Complete the following table.

| Configuration Item | Result |
| --- | --- |
| Role configured in PIM | |
| Eligible assignment created | |
| Activation policy requires MFA | |
| Activation policy requires approval | |
| Activation audit event found | |

---

## Reflection Questions

1. Why is Just‑In‑Time access safer than permanent administrative roles?
2. What risks exist if Power Platform Administrator roles are permanently assigned?
3. How could SOC teams detect suspicious role activation?
4. What additional policies could strengthen privileged access governance?

---

## Key Takeaways

After completing this lab you should understand:

- How Privileged Identity Management controls privileged access
- How to configure **eligible role assignments**
- How activation policies enforce **MFA and approval**
- How role activations appear in **Entra audit logs**

Privileged Identity Management is a critical control for **governing administrative access to Copilot, Power Platform, and Microsoft 365 services**.
