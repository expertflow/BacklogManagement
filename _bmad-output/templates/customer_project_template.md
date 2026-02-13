# Confluence Template: Customer Project Master

**Instructions:**
*   Use this template for every new Customer Project.
*   **Crucial:** Do not remove the "Page Properties" macro in the Summary section. It is used for reporting.
*   **Golden Thread:** Every row in the "Deliverables" table MUST have a linked JIRA Epic.

---

## 1. Project Summary
*(Wrap this table in a **Page Properties** macro for reporting)*

| Key | Value |
| :--- | :--- |
| **Customer Name** | [Enter Customer Name] |
| **Project Status** | [e.g., Pre-Sales, Implementation, UAT, Production, On-Hold] |
| **Health Status** | [e.g., Green (Happy), Yellow (Risk), Red (Critical)] |
| **Target Go-Live** | [Date] |
| **Project Manager** | @[Mention User] |
| **Tech Lead** | @[Mention User] |
| **JIRA Project Key** | [e.g., CUST-101] |
| **Contract/SOW** | [Link to Document] |

---

## 2. Deliverables & Phases (The Golden Thread)
*List the major phases or deliverables committed to the customer. Each must link to a JIRA Epic.*

| Phase / Deliverable | Description | Target Date | Status | **Linked JIRA Epic** |
| :--- | :--- | :--- | :--- | :--- |
| **Phase 1: MVP** | Core chat functionality and WhatsApp integration. | 2025-03-01 | Planning | [JIRA Epic Link] |
| **Phase 2: Reporting** | Custom reports and analytics dashboard. | 2025-04-15 | Pending | [JIRA Epic Link] |
| **Custom Feature A** | Specific customization for CRM integration. | TBD | Backlog | [JIRA Epic Link] |

---

## 3. Customer Environment
*Technical details of the deployment.*

| Component | Details |
| :--- | :--- |
| **Deployment Type** | [Cloud / On-Prem / Hybrid] |
| **Version** | [e.g., CX 4.7] |
| **Integrations** | [e.g., Salesforce, Cisco UCCE 12.5, Twilio] |
| **Access Details** | [Link to separate restricted page or Vault path] |

---

## 4. Feature Requests & Gaps
*Items requested by the customer that are NOT yet in the core product.*

*(Insert **Jira Issue/Filter Macro** here)*
> **JQL:** `project = "Your_Project" AND issuetype = "Feature Request" AND status != Done`

| Request | Business Value | Priority | JIRA Issue |
| :--- | :--- | :--- | :--- |
| [Short Title] | [Why do they need it?] | [High/Med/Low] | [Link] |

---

## 5. Live Project Board
*Real-time view of all open work for this customer.*

*(Insert **Jira Issue/Filter Macro** here)*
> **JQL:** `project = "Your_Project" AND type in (Story, Bug) AND statusCategory != Done ORDER BY priority DESC`

---

## 6. Meeting Minutes & Notes
*(Use the **Page Tree** macro or **Children Display** macro to show sub-pages for meeting notes)*

*   [Link to Meeting Note 1]
*   [Link to Meeting Note 2]
