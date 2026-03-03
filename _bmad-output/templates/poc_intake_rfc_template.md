# Confluence Template: PoC Intake RFC (Request for Comments)

**Instructions:**

- This document is **AI-generated** by the `bmm-analyst` or `bmm-pm` agent.
- The goal is to provide a structured **Go/No-Go** proposal for a new Proof of Concept.
- **Target Project:** All Epics and Stories will be created in the **PRS** (Presales) project.
- **Review Required:** Engineering and Product Management must approve the `poc-hack` strategy before scaffolding.

---

## 1. Opportunity Summary

*(Wrap this table in a **Page Properties** macro for reporting)*


| Key                        | Value                                          |
| -------------------------- | ---------------------------------------------- |
| **Customer Name**          | [Enter Customer Name]                          |
| **Sales Lead**             | @[Mention Sales Lead]                          |
| **Est. Deal Size / ARR**   | [e.g., $150k ARR]                              |
| **PoC Deadline**           | [Date]                                         |
| **Success Criteria Count** | [e.g., 3 Critical Wins]                        |
| **Proposed PRS Epic**      | [e.g., PoC: [Customer] - WhatsApp Integration] |


---

## 2. The "3-5 Success Criteria" (The Technical Win)

*What specifically must be demonstrated to win the PO?*


| ID        | Success Criterion            | Metric for Success                           | JIRA PRS Story    |
| --------- | ---------------------------- | -------------------------------------------- | ----------------- |
| **SC-01** | [e.g., WhatsApp integration] | [e.g., 500 concurrent sessions handled]      | [Link to PRS-XXX] |
| **SC-02** | [e.g., SSO Login]            | [e.g., Customer's Azure AD Login functional] | [Link to PRS-XXX] |
| **SC-03** | [e.g., Real-time Wallboard]  | [e.g., Custom KPI displayed in dashboard]    | [Link to PRS-XXX] |


---

## 3. The `poc-hack` Strategy (Risk & Speed)

*To meet the deadline, where are we intentionally taking on Technical Debt?*


| Component    | The "Hack" (Speed)                 | The "Proper" Build (Post-POV)  | Risk Level |
| ------------ | ---------------------------------- | ------------------------------ | ---------- |
| **Database** | [e.g., Use hardcoded mock data]    | Full SQL Schema integration    | Low        |
| **Security** | [e.g., Temporary bypass for SSO]   | Full Azure AD OIDC Integration | High       |
| **Scaling**  | [e.g., Single instance deployment] | Multi-node high-availability   | Med        |


---

## 4. Gap Analysis (Feature Requests)

*What features are requested that do NOT currently exist in the Product Roadmap?*


| Feature Gap | Priority | Roadmap Alignment                       | Status           |
| ----------- | -------- | --------------------------------------- | ---------------- |
| [Gap Name]  | [H/M/L]  | [e.g., Planned for Q4 / Not in Roadmap] | [Pending Review] |


---

## 5. Proposed Resource Allocation

*AI-generated estimates for the PoC execution.*

- **Solution Architect (SA) Hours:** [e.g., 16h]
- **Development Hours:** [e.g., 24h]
- **Infrastructure/Cloud Cost:** [e.g., $50 / month]

---

## 6. Approval Log

*Sign-off required BEFORE creating the PRS Epic and Stories.*


| Role                   | Approver        | Date | Decision           |
| ---------------------- | --------------- | ---- | ------------------ |
| **Product Management** | @[Mention User] |      | [Pending/Approved] |
| **Engineering Lead**   | @[Mention User] |      | [Pending/Approved] |
| **Sales Lead**         | @[Mention User] |      | [Pending/Approved] |


