# PI Planning Dashboard Specification: The Golden Thread View

**Purpose:** To replace static planning pages with dynamic, real-time dashboards that enforce alignment between Customer Commitments and Team Execution.

---

## 1. JIRA Filters (JQL)

Create these filters in JIRA. You will use their specific Filter IDs in Confluence macros.

### Filter A: "PI Customer Commitments"
*   **Goal:** Show all high-level deliverables promised to customers for this specific PI.
*   **JQL:**
    ```sql
    issuetype = Epic 
    AND "Epic Classification" = "Customer Deliverable" 
    AND "Target PI" = "Q2-2025" 
    ORDER BY "Customer" ASC, priority DESC
    ```

### Filter B: "PI Feature Roadmap"
*   **Goal:** Show the actual work (Features) teams are doing to deliver on those commitments.
*   **JQL:**
    ```sql
    issuetype = Feature 
    AND "Target PI" = "Q2-2025" 
    ORDER BY "Team" ASC, "Target End Date" ASC
    ```

### Filter C: "Risk Board - Unplanned Commitments"
*   **Goal:** Identify Customer Deliverables that have NO linked work (Features) planned.
*   **JQL:**
    ```sql
    issuetype = Epic 
    AND "Epic Classification" = "Customer Deliverable" 
    AND "Target PI" = "Q2-2025" 
    AND issueFunction not in hasLinkType("Is Delivered By")
    ```
    *(Note: This advanced JQL requires ScriptRunner. If unavailable, use manual review of Filter A).*

---

## 2. Confluence Page Layout (The Dashboard)

Update your **PI Planning (Qx-20xx)** page template to include these sections.

### Section 1: Customer Obligations (The "Why")
*   **Macro:** `Jira Issues`
*   **Source:** Filter A ("PI Customer Commitments")
*   **Columns to Display:**
    *   `Customer` (Custom Field)
    *   `Summary` (The Deliverable Name)
    *   `Priority`
    *   `Status`
    *   `Confluence Link` (The link back to the Customer Project Page)

### Section 2: Execution Plan (The "What")
*   **Macro:** `Jira Issues`
*   **Source:** Filter B ("PI Feature Roadmap")
*   **Columns to Display:**
    *   `Team`
    *   `Summary` (The Feature Name)
    *   `Status`
    *   `Story Points` / `Estimates`
    *   **`Linked Issues`** (CRITICAL: This shows the "Is Delivered By" link to the Epic)

### Section 3: Risk Board (The Gaps)
*   **Macro:** `Jira Issues`
*   **Source:** Filter C ("Risk Board")
*   **Visual Warning:** *Place this section in a "Warning" macro box.*
*   **Instruction:** "WARNING: The following Customer Deliverables are committed for this PI but have NO linked Features in the roadmap."

---

## 3. The Planning Workflow (How to use this during PI Planning)

1.  **Pre-Planning:** Product Management ensures all "Customer Deliverable" Epics in JIRA are tagged with the correct `Target PI`.
2.  **During Planning:**
    *   Review **Section 1** to confirm the scope of commitments.
    *   Teams break down Epics into **Features** and tag them with `Target PI`.
    *   Teams **LINK** their Features to the Customer Epics using the "Delivers" link.
3.  **Review:**
    *   Look at **Section 3**. Is it empty? If not, you are missing work.
    *   Look at **Section 2**. Does every Feature have a link? If not, is it necessary?
