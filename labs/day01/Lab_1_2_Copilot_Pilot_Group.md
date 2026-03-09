
# Lab 1.2 — Assign Copilot License and Configure Pilot Group

## Course

Enterprise Copilot Governance, Security, and Administration

## Lab Duration

Approx. **45 minutes**

## Lab Objective

In this lab you will practice the **recommended Copilot rollout approach** used in enterprise environments: deploying the service to a **pilot security group** rather than enabling it for all users.

You will:

1. Create a **pilot security group in Microsoft Entra ID**
2. Configure **group-based licensing**
3. Assign a Microsoft 365 license to the group
4. Verify Copilot configuration controls in the **Microsoft 365 Admin Center**
5. Document the pilot rollout configuration

> NOTE: Microsoft 365 Developer Tenants typically **do not include Microsoft 365 Copilot licenses**.  
> For this lab you will simulate the rollout using the tenant’s available Microsoft 365 license (for example Microsoft 365 E5 Developer).  
> The **group-based licensing process is identical** to the Copilot rollout process used in production tenants.

---

## Lab Scenario

Your organization is preparing to deploy **Microsoft 365 Copilot**.

Enterprise best practice is to:

* Deploy Copilot to a **pilot group**
* Validate user experience and governance controls
* Expand rollout gradually

You are tasked with creating the pilot group and configuring licensing for that group.

---

## Lab Environment

Students will use:

* Microsoft 365 Developer Tenant
* Microsoft Entra Admin Center
* Microsoft 365 Admin Center

---

## Required Permissions

To complete this lab, the student account must have one of the following roles:

### Recommended Role

Global Administrator

### Alternative Roles

| Task | Role Required |
| ----- | ----- |
| Create Entra security group | User Administrator or Global Administrator |
| Configure group licensing | License Administrator or Global Administrator |
| View Copilot settings | Global Administrator |

In most Microsoft 365 Developer Tenants the default user account is already **Global Administrator**.

---

## Architecture Concept

Enterprise Copilot rollouts typically follow this model:

```text
Tenant
   |
Pilot Security Group
   |
Group-Based Licensing
   |
Copilot Enabled Users
```

This approach allows administrators to:

* Control rollout scope
* Quickly remove users if issues occur
* Apply policies consistently

---

## Task 1 — Create the Copilot Pilot Security Group

### Step 1

Open the **Microsoft Entra Admin Center**

<https://entra.microsoft.com>

---

### Step 2

Navigate to: **Groups**

Select **New group**.

---

## Step 3

Configure the group.

| Setting | Value |
| ------ | ------ |
| Group type | Security |
| Group name | Copilot-Pilot |
| Description | Pilot users for Copilot rollout |
| Membership type | Assigned |

Click **Create**.

---

## Step 4

Add members to the group.

Open the newly created group and select: **Members → Add members**

Add:

* Your administrator account
* At least one additional user account in the tenant

Click **Select**.

---

## Task 2 — Configure Group-Based Licensing

Group-based licensing automatically assigns licenses to all members of a group.

Navigate to <https://admin.microsoft.com>

* Under **Teams & groups**, select **Active teams and groups**
* In **Search all teams and groups**, enter **Copilot** to search for your new group
* Select the **Copilot-Pilot** group and select **Licenses and apps**
* Select the available licenses
* Click **Save changes**

---

## Task 3 — Verify License Assignment to Users

### Step 1

Navigate to: **Users** | **Active users**

---

### Step 2

Select a user in the group.

---

### Step 3

Navigate to:

**Licenses and apps**

Verify the license is assigned **via group**.

The assignment source should show:

**Group-based assignment**.

---

## Task 4 — Verify Copilot Settings in Microsoft 365 Admin Center

Copilot configuration settings appear in the Microsoft 365 Admin Center when the service is available in the tenant.

---

### Step 1

Open the **Microsoft 365 Admin Center**

<https://admin.microsoft.com>

---

### Step 2

Navigate to:

**Copilot** | **Settings**

---

### Step 3

Possible results in a Developer Tenant:

| Result | Explanation |
| ------ | ------ |
| Copilot settings visible | Tenant has Copilot features available |
| Copilot settings not visible | Tenant does not have Copilot licenses |

---

## Task 5 — Document the Pilot Rollout Configuration

Complete the documentation table.

| Configuration Item | Result |
| --- | --- |
| Pilot Group Name | |
| Number of Users in Pilot | |
| License Assigned | |
| Group-Based Licensing Enabled | Yes / No |
| Copilot Settings Page Visible | Yes / No |

---

## Reflection Questions

Answer the following:

1. Why is group-based licensing recommended for Copilot rollouts?
2. What advantages does a pilot group provide during deployment?
3. What risks exist if Copilot is enabled for all users immediately?
4. What governance checks should occur before expanding the rollout?

---

## Key Takeaways

After completing this lab you should understand:

* How to create a pilot group in Entra ID
* How group-based licensing works
* Why pilot groups are used for Copilot rollout
* How administrators verify Copilot configuration in the tenant

Group-based licensing is a **core administrative pattern used for Copilot, security tools, and enterprise applications across Microsoft 365**.
