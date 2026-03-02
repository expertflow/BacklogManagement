# Expertflow Global Context (The Company Bible)

**Status:** Master Reference (Synced from Confluence)  
**Last Updated:** 2026-02-27

---

## 1. Company Vision & Strategic North Stars
- **AI-Driven Self-Service:** Transform complexity into clarity. Move from "Guided Install" to "One-Click/Self-Service" deployment.
- **Cloud-First & GitOps:** Standardize on Kubernetes (RKE2), ArgoCD, and automated scaling.
- **Deep CRM Integration:** Native CTI connectors for Salesforce, SAP (V2), MS Dynamics, Odoo, and HubSpot.

---

## 2. The "Speed-Native" Work Hierarchy (SAFe-lite)
| Level | Type | Purpose |
| :--- | :--- | :--- |
| **Level 0** | **Initiative** | High-level strategic theme (Portfolio Backlog). |
| **Level 1** | **Epic / Feature** | Functional or technical outcome. |
| **Level 2** | **Story / Bug / Task** | The unit of value and effort. |
| **Level 3** | **Sub-task** | Unit of action. |

---

## 3. Universal Work Categories & Investment Health
All work must be tagged with one of the following to ensure balanced investment:
- **Business Feature:** Includes Strategic Vision and PoC Blockers.
- **Customer Feedback:** Includes mid-project pivots and live support requests.
- **Enabler:** Infrastructure, architecture, and R&D.
- **Technical Debt:** Stability and performance (Includes PoC Hacks).
- **Bug / Vulnerability:** Security patches and production fixes.

---

## 4. Technical Mandates & CI Gates
- **Branching:** GitFlow-inspired (Feature -> Develop -> Main).
- **CI Gates:** No MR/PR is accepted without:
    - SonarQube Scan (Clean).
    - Security Vulnerability Scan.
    - Behavior-Driven Tests (BDD) & TDD (Unit/Integration).
- **System Demos:** Conducted after each iteration to show practical business value.

---

## 5. The Golden Chain Rule
Every Customer Commitment (`CUS-`) must be **BLOCKED BY** a Product Deliverable (`EF-INTERNAL`).
