# Customer & Partner Feedback Loop Strategy

**Goal:** Ensure all external feedback (Mid-Project or Post-Production) is captured and prioritized without causing "Silent Scope Creep" or disrupting the Speed-Native flow.

---

## 1. Mid-Project Change Requests (The "Pivot" Flow)
*Trigger: A customer requests a change or addition to a project that is already in Phase 4 (Implementation).*

### 1.1 Triage & Classification (AI-Analyst)
*   **Minor Adjustment:** (e.g., UX tweaks, wording changes). Direct to **Level 2 Story** in the current Epic.
*   **Scope Drift:** (e.g., New feature, different integration).
    *   **Action:** Trigger the **`correct-course`** BMAD workflow.
    *   **Commercial Check:** AI flags the Project Manager (PM) to determine if this requires an addendum to the SOW.
    *   **Golden Chain:** New work must be linked to an **EF-INTERNAL** Epic via "Is Blocked By."

### 1.2 Impact Analysis
The `correct-course` workflow calculates the impact on the current **Team WIP Limit** and **Target Go-Live Date**.
*   **Decision:** The PM/PO must explicitly "Swap" an existing story for the new request or push the Go-Live date.

---

## 2. Post-Production / Live Feedback (The "Continuous Discovery" Flow)
*Trigger: Feedback from a live customer via Support Tickets, QBRs, or Partner Portals.*

### 2.1 The "In-bound" Triage
*   **Bugs/Vulnerabilities:** Direct to the **"Fast-Track"** queue for the next available capacity slot.
*   **Feature Requests:**
    *   **Action:** Create a **Level 1 Epic** in the `EF-INTERNAL` project.
    *   **Label:** `customer-request`, `live-feedback`.
    *   **Metadata:** Link to the Hubspot Customer record and the Partner (if applicable).

### 2.2 The "Triad" Refinement (PO + Tech Lead + Architect)
*   **Promotion Criteria:** Live feedback is reviewed in the bi-weekly **Triad Sync** using the **AI-Native WSJF (Weighted Shortest Job First)** formula.
*   **The Value Formula:**
    `Priority Score = [ (U * 2) + (C / 10,000) + (S * 1.5) + (R * 3) ] / Estimated Story Points`

| Variable | Name | Definition | Scale |
| :--- | :--- | :--- | :--- |
| **U** | Usage Impact | Number of unique customers/partners requesting the feature. | 1 pt per customer |
| **C** | Commercial Weight | Total SOW/ARR value of the requesting customers. | 1 pt per $10k |
| **S** | Strategic Alignment | Platform-fit (Core vs. Adapter) as defined by the Architect. | 1-10 |
| **R** | Retention Risk | Is this a "nice-to-have" or a critical go-live blocker? | 1 (Low) - 5 (Critical) |
| **Points** | Job Size | Technical effort estimated by the AI Architect / Dev Lead. | Story Points |

*   **Promotion Threshold:** Any feedback item hitting a score of **2.5 or higher** (Adjustable per PI) is automatically promoted from the `live-feedback` Epic into a **Draft Story** for the next sprint.
*   **Automation:** The AI Analyst calculates the "Value" numerator from CRM/Support data; the AI Architect estimates the "Size" denominator from the codebase.

---

## 3. Partner-Specific Feedback
*   **Rule:** Partner feedback is treated with the same urgency as direct Customer feedback.
*   **Aggregation:** AI Analyst aggregates feedback from the same Partner across multiple projects to identify **Market Patterns** (e.g., "3 different Partners in Nigeria are asking for XYZ integration").

---

## 4. Visibility & Closing the Loop
*   **The "Feedback Dashboard":** A Confluence page showing the status of all Customer/Partner requests (Backlog, In Roadmap, In Progress, Done).
*   **Automatic Notification:** When an `EF-INTERNAL` story linked to a customer request is marked `Done`, the AI Analyst triggers a notification to the PM/Presales lead to "Close the Loop" with the customer.
