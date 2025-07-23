# 🧾 Salesforce Admin Project: Customer Support Portal

**Organization:** TechTrend Innovations  
**Prepared By:** Ancy Winston D’Silva  
**Objective:** Build a scalable Salesforce-based Customer Support Portal for Enterprise and SMB clients, featuring automation, customization, and reporting.

---

## 🧩 1. Project Overview

- **Project Goal:** Build a Customer Support Portal in Salesforce
- **Target Users:** Enterprise and SMB Customers
- **Scope of Work:** Customization, Automation, Analytics

---

## 🔧 2. Custom Fields on Case Object

| Field Name            | Data Type | Values                                           | Description                         |
| --------------------- | --------- | ------------------------------------------------ | ----------------------------------- |
| Product Type          | Picklist  | Software, Hardware                               | Type of product the case relates to |
| Support Tier          | Picklist  | Basic, Premium, Platinum                         | Level of support provided           |
| Resolution Time       | Number    | —                                                | Time taken to resolve the case      |
| Customer Satisfaction | Picklist  | Very Satisfied, Satisfied, Neutral, Dissatisfied | Customer feedback on resolution     |

📸 **Figure 1:** Screenshot of Case Object → Fields & Relationships

---

## 🏗️ 3. Support Process Setup

- **Issue:** Error encountered when creating Record Type – missing Support Process  
  📸 **Figure 2:** Screenshot of error message

- **Resolution:** Created a Standard Support Process

  - **Status values:** New, In Progress, Escalated, Closed  
    📸 **Figure 3:** Screenshot of Support Process configuration

---

## 🧾 4. Record Types Configuration

### ✅ Enterprise Record Type

- Name: `Enterprise`
- Support Process: Standard Support Process
- Page Layout: Enterprise Layout

### ✅ SMB Record Type

- Name: `SMB`
- Support Process: Standard Support Process
- Page Layout: SMB Layout

📸 **Figure 4:** Screenshot of Record Type list

---

## 🖼️ 5. Page Layouts

### 🏢 Enterprise Layout

**Sections & Fields:**

- Case Overview: Case Number, Status, Subject, Priority
- Customer Details: Contact Name, Account Name
- Enterprise Details: Product Type, Support Tier, Resolution Time, Customer Satisfaction
- Case Notes: Description, Closed Date
- Web Details: (collapsed)

📸 **Figure 5:** Screenshot of Enterprise Page Layout

### 🏠 SMB Layout

Follows similar structure to Enterprise Layout  
**Adjustments:**

- Product Type: Software-only
- Support Tier: Basic, Premium

📸 **Figure 6:** Screenshot of SMB Page Layout

---

## 🔁 6. Picklist Value Customization

| Record Type | Product Type       | Support Tier   |
| ----------- | ------------------ | -------------- |
| Enterprise  | Hardware, Software | Platinum       |
| SMB         | Software           | Basic, Premium |

📸 **Figure 7:** Screenshot of Picklist Value Settings

---

## 🧪 7. Case Creation Testing

- Created test cases for both Record Types
- Verified:
  - Field visibility
  - Page layout consistency
  - Picklist behavior

📸 **Figure 8:** "New Case" record type selection  
📸 **Figure 9:** Enterprise layout view  
📸 **Figure 10:** SMB layout view

---

## 📈 8. Next Steps

- ✅ Implement Validation Rules
- ✅ Set up Flow Automation for escalations and email alerts
- ✅ Build Custom Reports (e.g., Average Resolution Time)
- ✅ Design Dashboards for KPIs (e.g., Customer Satisfaction Trends)

---

## 🔍 Case Status Behavior – Salesforce Observations

**Behavior:**

- `Closed` is visible in:

  - Picklist setup
  - Support Process config
  - Record Type picklist settings

- But NOT selectable:
  - When creating/editing case records using standard UI

**Still Works via:**

- Kanban View drag-and-drop
- Automation (Flows, Apex, Process Builder)
- API/backend logic

**Note:** Custom status values like `Resolved` do not face this issue.

### ✅ Conclusion:

Salesforce applies special logic to standard status values like `Closed`, treating them as final system states. Manual selection is restricted in UI forms. Workarounds:

- Use automation to close cases
- Introduce intermediate status like `Resolved`

---

> 📌 This is a personal practice project to apply and showcase Salesforce Admin skills, built step-by-step for real-world readiness and certification preparation.
