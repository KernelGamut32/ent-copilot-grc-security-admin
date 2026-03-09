
# Lab 1.3 — Create and Enforce a Power Platform DLP Policy

## Course

Enterprise Copilot Governance, Security, and Administration

## Lab Duration

~60 minutes

## Lab Objective

In this lab you will create and test a **Data Loss Prevention (DLP) policy** in the **Power Platform Admin Center**.

You will:

1. Create a **tenant-wide DLP policy**
2. Classify connectors into **Business** and **Blocked** groups
3. Allow **SharePoint, Dataverse, and Outlook** connectors
4. Block the **HTTP connector**
5. Test the enforcement behavior in **Power Automate**

This exercise demonstrates how organizations enforce **data boundaries between trusted enterprise services and external endpoints**.

---

## Scenario

Your organization is preparing to deploy **Microsoft Copilot and Power Platform solutions**.

To protect sensitive business data, administrators must enforce **connector governance** using Power Platform DLP policies.

The governance requirement is:

| Connector | Classification |
| --- | --- |
| SharePoint | Business |
| Dataverse | Business |
| Office 365 Outlook | Business |
| HTTP | Blocked |

The HTTP connector allows sending data to arbitrary external APIs and must be blocked to prevent data exfiltration.

You will implement this policy and test the behavior.

---

## Lab Environment

Students will perform the lab using:

* Microsoft 365 Developer Tenant
* Power Platform Admin Center
* Power Automate (Flow)

---

## Required Permissions

Students must have one of the following roles:

### Recommended

Global Administrator

### Alternative

Power Platform Administrator

These roles allow:

* Creating DLP policies
* Viewing environments
* Managing connectors

---

## Concepts Covered

Power Platform DLP policies organize connectors into three groups:

| Group | Purpose |
| --- | --- |
| Business | Approved enterprise connectors |
| Non-Business | Consumer connectors |
| Blocked | Completely prohibited connectors |

Flows **cannot combine Business and Non-Business connectors**, and **Blocked connectors cannot be used at all**.

---

## Task 1 — Open the Power Platform Admin Center

1. Open the Power Platform Admin Center:

    <https://admin.powerplatform.microsoft.com>

2. Sign in using your administrator account.

---

## Task 2 — Create the DLP Policy

1. In the left navigation pane select: **Security** | **Data and privacy**

2. Click **Data policy** and **New policy**.

3. Enter the following:

| Setting | Value |
| --- | --- |
| Policy name | Copilot-Governance-DLP |

Click **Next**.

---

## Task 3 — Classify Connectors

The connector classification screen will appear.

Search and configure the following connectors.

### Step 1 — Add Business Connectors

Move the following connectors to **Business**:

| Connector |
| --- |
| SharePoint |
| Office 365 Outlook |
| Dataverse |

These connectors represent trusted enterprise data sources.

---

### Step 2 — Block the HTTP Connector

Search for: **HTTP**

Move **HTTP** to the **Blocked** category.

Blocking HTTP prevents flows from sending data to arbitrary external services.

---

### Step 3 — Review Configuration

Your connector configuration should look like this:

| Group | Connectors |
| --- | --- |
| Business | SharePoint, Office 365 Outlook, Dataverse |
| Blocked | HTTP |

Click **Next** and **Next**.

---

## Task 4 — Apply the Policy to the Tenant

1. Choose environments where the policy applies.

For this lab choose: **All environments**

This ensures the policy applies to the entire tenant.

Click **Next**.

---

## Task 5 — Create the Policy

Review the configuration.

Click **Create policy**.

The policy may take **1–2 minutes to propagate** across environments.

---

## Task 6 — Validate Policy Enforcement

Now test whether the policy blocks the HTTP connector.

---

## Step 1 — Open Power Automate

Navigate to:

<https://make.powerautomate.com>

---

## Step 2 — Create a Test Flow

1. Select **Create**
2. Choose **Instant cloud flow**
3. Select trigger: **Manually trigger a flow**

Click **Create**.

---

## Step 3 — Attempt to Use HTTP Connector

1. Click **New Step**
2. Search for: **HTTP**
3. Add the HTTP action and set a URL and Method
4. Click **Save**

---

## Expected Result

The HTTP connector should show a **policy restriction message** indicating it is blocked by a DLP policy.

Students may see:

* The connector unavailable
* A policy restriction warning

This confirms the DLP policy is being enforced.

---

## Task 7 — Verify Allowed Connectors

1. In the same flow click **New Step**.
2. Search for:

* SharePoint
* Office 365 Outlook

These connectors should be available because they are in the **Business group**.

---

## Task 8 — Document Results

Complete the following table.

| Configuration Item | Result |
| --- | --- |
| Policy Name | |
| Scope | |
| Business Connectors | |
| Blocked Connectors | |
| HTTP Connector Behavior | |
| SharePoint Connector Behavior | |

---

## Reflection Questions

1. Why is the HTTP connector considered high risk?
2. How does Power Platform DLP prevent data exfiltration?
3. What would happen if SharePoint were placed in the Non-Business group?
4. Why should DLP policies typically be tested in pilot environments before global deployment?

---

## Key Takeaways

After completing this lab you should understand:

* How Power Platform DLP policies control connector usage
* Why HTTP connectors are commonly blocked in enterprise environments
* How connector classification enforces data boundaries
* How DLP policies are validated using Power Automate

These controls are critical for **governing Copilot, Power Automate, and Power Apps solutions in enterprise environments**.
