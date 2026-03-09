
# Lab 1.4 — Provision a Managed Environment

## Course

Enterprise Copilot Governance, Security, and Administration

## Lab Duration

~60 minutes

## Lab Objective

In this lab you will create a **production-style Power Platform environment**, enable **Managed Environment governance features**, and configure **Dataverse auditing**.

You will also configure **administrative access using Dataverse roles** instead of tenant-wide roles like Global Administrator.

This mirrors enterprise governance practices where environment administration is **delegated to platform administrators rather than tenant administrators**.

---

## Lab Scenario

Your organization is preparing to deploy **enterprise Power Platform and Copilot-based solutions**.

To maintain governance and separation of duties, the platform team will:

* Create a **production environment**
* Enable **Managed Environment governance features**
* Turn on **Dataverse auditing**
* Assign environment administrators using **Dataverse roles**

You have been asked to provision this environment according to governance standards.

---

## Lab Environment

Students will perform this lab using:

* Microsoft 365 Developer Tenant
* Power Platform Admin Center
* Power Apps / Dataverse

---

## Required Permissions

To complete this lab the student account must have one of the following roles:

### Recommended

Power Platform Administrator

### Alternative

Global Administrator

Power Platform Administrator is preferred because enterprise governance typically avoids using Global Admin for environment management.

---

## Concepts Covered

## Power Platform Environments

Environments provide isolation boundaries for:

* Apps
* Flows
* Dataverse databases
* Copilot Studio agents

## Managed Environments

Managed Environments provide governance capabilities such as:

* Usage insights
* Sharing limits
* Weekly governance digest emails
* Environment administration controls

## Dataverse Roles

Dataverse roles provide **environment-scoped administration**, including:

| Role | Purpose |
| ----- | ----- |
| System Administrator | Full environment administration |
| System Customizer | App customization |
| Environment Maker | App creation |

Organizations should assign **System Administrator roles within Dataverse rather than Global Admin roles**.

---

## Task 1 — Open the Power Platform Admin Center

1. Navigate to:

    <https://admin.powerplatform.microsoft.com>

2. Sign in with your administrator account.

---

## Task 2 — Create a Production Environment

1. In the left navigation pane select: **Manage** | **Environments**

2. Click **+ New**.

3. Configure the environment:

    | Setting | Value |
    | --- | --- |
    | Name | Corp-Prod-Apps |
    | Region | Default region |
    | Type | Developer (should be Production) |
    | Add a Dataverse data store | Yes |

    Click **Next**.

4. Accept the default Dataverse settings and click **Save**.

Provisioning may take several minutes.

---

## Task 3 — Apply Naming Standards

Enterprise governance typically enforces naming standards.

For this lab we will use the standard:

```text
Corp-<EnvironmentType>-<Workload>
```

Examples:

* Corp-Prod-Apps
* Corp-Test-Apps
* Corp-Dev-Apps

Verify the environment name follows this standard.

---

## Task 4 — Enable Managed Environment

1. In the Power Platform Admin Center open the environment: **Corp-Prod-Apps**

2. Locate **Managed environments**.

3. Select **Enable Managed Environments**.

4. Accept the default settings and confirm.

The environment is now governed using Managed Environment capabilities.

---

## Task 5 — Enable Dataverse Auditing

Dataverse auditing tracks data changes for compliance and investigation.

---

### Step 1 — Open Environment Settings

1. In the environment select: **Settings → Product → Features**

---

### Step 2 — Enable Auditing

Locate **Auditing**.

Enable:

* **Send audit logs to Microsoft Purview**

Save the configuration.

---

## Task 6 — Assign Dataverse System Administrator Role

Instead of using Global Admin permissions, environment administration should be assigned through Dataverse roles.

---

### Step 1 — Open Power Apps

Navigate to:

<https://make.powerapps.com>

---

### Step 2 — Select Environment

From the environment selector in the top right choose: **Corp-Prod-Apps**

---

### Step 3 — Open Security Roles

Navigate to: **Settings** | **Security roles**

---

### Step 4 — Review Role Definitions

* Review role designations
* Review settings for **Users** and **Teams**
* Explore modifications that can be implemented

---

## Task 7 — Verify Environment Administration Model

Confirm:

| Governance Control | Status |
| --- | --- |
| Production environment created | |
| Managed Environment enabled | |
| Dataverse auditing enabled | |

---

## Reflection Questions

1. Why should organizations avoid using Global Administrator for Power Platform environments?
2. What governance capabilities are enabled by Managed Environments?
3. Why is Dataverse auditing important for compliance?
4. How do environment-scoped roles improve security governance?

---

## Key Takeaways

After completing this lab you should understand:

* How to create Power Platform environments
* How Managed Environments enforce governance
* How Dataverse auditing supports compliance monitoring
* Why environment administration should use Dataverse roles instead of Global Admin

These practices are essential for **secure enterprise deployment of Copilot, Power Apps, and Power Automate solutions**.
