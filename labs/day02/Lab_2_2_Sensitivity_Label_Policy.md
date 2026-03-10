
# Lab 2.2 — Create and Test a Sensitivity Label Policy

## Course

Enterprise Copilot Governance, Security, and Administration

## Lab Duration

~60 minutes

## Lab Objective

In this lab you will create a **Microsoft Purview Sensitivity Label** that protects confidential internal documents using **encryption and mandatory labeling**.

You will:

1. Create a **Sensitivity Label** named **Confidential – Internal Only**
2. Configure **encryption permissions restricted to an internal group**
3. Publish the label via a **label policy**
4. Apply the label to documents stored in a **SharePoint document library**
5. Verify that users outside the authorized group **cannot access encrypted content**

This exercise demonstrates how **Microsoft Purview Information Protection controls Copilot grounding data access**, since Copilot respects the same access and encryption boundaries applied to Microsoft 365 content.

> NOTE: Microsoft 365 Developer Tenants typically **do not include Copilot licenses**.  
> Instead of testing Copilot responses directly, this lab verifies the **underlying access control enforcement** that Copilot also respects.

---

## Lab Scenario

Your organization is deploying Microsoft 365 Copilot and must ensure that **sensitive internal documents are protected**.

Security policy requires:

- Sensitive documents must be labeled **Confidential – Internal Only**
- Content must be **encrypted**
- Only authorized internal users may access the data

Copilot must also **respect these protections**, meaning it cannot retrieve or summarize encrypted documents for unauthorized users.

You will implement the label and test enforcement.

---

## Lab Environment

Students will perform the lab using:

- Microsoft 365 Developer Tenant
- Microsoft Purview Compliance Portal
- Microsoft SharePoint Online

All students will use the **same tenant**.

---

## Required Permissions

To complete this lab the student account must have one of the following roles:

### Recommended

Compliance Administrator

### Alternative Roles

| Role | Capability |
| ----- | ----- |
| Global Administrator | Full access |
| Information Protection Administrator | Manage sensitivity labels |

These roles allow:

- Creating sensitivity labels
- Publishing label policies
- Managing encryption settings

---

## Concepts Covered

### Sensitivity Labels

Sensitivity labels allow organizations to classify and protect data using:

- Encryption
- Access restrictions
- Mandatory labeling
- Content markings

### Copilot Data Protection

Microsoft Copilot respects:

- SharePoint permissions
- Microsoft Purview sensitivity labels
- Encryption policies

If a user cannot access encrypted content, **Copilot also cannot access or summarize it**.

---

### Task 1 — Open Microsoft Purview

1. Navigate to:

    <https://purview.microsoft.com>

2. Sign in with your administrator account.

---

### Task 2 — Create a Sensitivity Label

1. In the left navigation pane select: **Solutions → Information Protection → Sensitivity labels**

2. Click **Create a label**.

---

## Configure Label Settings

Enter the following:

| Setting | Value |
| --- | --- |
| Name | Confidential – Internal Only |
| Description | Internal confidential documents |
| Display name | Confidential – Internal Only |

Click **Next**.

---

### Task 3 — Configure Encryption

1. Enable **Encryption**.

2. Configure permissions.

Select:

**Assign permissions now**.

---

## Configure Authorized Users

Add an internal group or users.

Example:

- Your administrator account
- A small group of approved users

Permissions:

| Permission | Value |
| --- | --- |
| View | Allowed |
| Edit | Allowed |
| Export | Allowed |

Click **Next**.

---

### Task 4 — Configure Content Marking

Optional but recommended.

Enable:

- Header
- Watermark

Example watermark text:

Confidential – Internal Only

Click **Next**.

---

### Task 5 — Publish the Label

1. Select **Publish label**.

2. Create a **new label policy**.

Policy settings:

| Setting | Value |
| --- | --- |
| Policy name | Internal Confidential Policy |
| Users or groups | All users |
| Mandatory labeling | Enabled |

Finish the wizard.

Policy propagation may take several minutes.

---

### Task 6 — Create a Test SharePoint Library

1. Navigate to:

    <https://portal.office.com>

2. Open **SharePoint**.

3. Create a new site if needed.

Example site name:

Copilot-Governance-Lab

---

## Create a Document Library

1. In the SharePoint site select: **New → Document Library**

Name:

Confidential Documents

---

### Task 7 — Upload a Test Document

1. Upload any sample document.

Example:

confidential-report.docx

---

### Task 8 — Apply the Sensitivity Label

1. Open the document in **Word Online**.

2. Select: **Sensitivity → Confidential – Internal Only**

3. Save the document.

The document is now:

- Classified
- Encrypted
- Restricted to authorized users

---

### Task 9 — Test Access Restrictions

Ask another student **not included in the authorized users list** to open the document.

Expected result:

Access is denied or restricted due to encryption.

This demonstrates the protection boundary enforced by Purview.

Since Copilot respects these same boundaries, Copilot also **cannot access this document for unauthorized users**.

---

### Task 10 — Review Label Activity

Return to **Microsoft Purview**.

Navigate to: **Activity explorer**

Filter for:

- Sensitivity label applied
- File activities

Confirm the label application event appears.

---

### Task 11 — Document Results

Complete the following table.

| Configuration Item | Result |
| --- | --- |
| Sensitivity label created | |
| Encryption enabled | |
| Label policy published | |
| SharePoint document labeled | |
| Unauthorized access blocked | |

---

## Reflection Questions

1. Why are sensitivity labels critical for Copilot data protection?
2. How does encryption differ from SharePoint permissions?
3. What risks exist if confidential data is not labeled?
4. How can organizations ensure users consistently apply labels?

---

## Key Takeaways

After completing this lab you should understand:

- How to create Microsoft Purview sensitivity labels
- How encryption restricts access to confidential content
- How label policies enforce classification across users
- How sensitivity labels protect data used by Copilot

Sensitivity labels are one of the **most important governance controls for protecting enterprise data accessed by Microsoft 365 Copilot**.
