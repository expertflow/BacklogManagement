# PI Planning Dashboard Specification V2: The Cross-Project Handshake

**Purpose:** To visualize the alignment between **Customer Demand** (Customer JIRA Projects like `NHCAP`, `MPCP`) and **Product Supply** (Team JIRA Projects like `CIM`, `CX`).

**Core Concept:** The "Handshake" is a JIRA Link (`Implements` / `Is Implemented By`) connecting a Customer Epic to a Product Feature/Story.

---

## 1. JIRA Filter Strategy

We need two distinct sets of filters: one for the "What we need" (Demand) and one for "What we are doing" (Supply).

### A. The Demand Filter (Customer Projects)
*   **Goal:** List all major deliverables from all Customer projects due in the upcoming PI.
*   **Challenge:** You have many customer projects (`NHCAP`, `MPCP`, `BE`, etc.).
*   **Strategy:** Use a `Category` or a specific list of projects.
*   **JQL:**
    ```sql
    project in (NHCAP, MPCP, BE, "Customer A", "Customer B") 
    AND issuetype = Epic 
    AND (
        "Target Release Date" >= 2025-01-01 AND "Target Release Date" <= 2025-03-31
        OR fixVersion = "Q1-2025"
    )
    ORDER BY "Target Release Date" ASC
    ```

### B. The Supply Filter (Product Teams)
*   **Goal:** List the features the internal teams (`CIM`, `CX`, `Voice`) are building in this PI.
*   **JQL:**
    ```sql
    project in (CIM, CX, "Voice Subsystem") 
    AND issuetype in (Feature, Story) 
    AND "Target PI" = "Q1-2025" 
    ORDER BY "Team" ASC
    ```

---

## 2. Confluence Dashboard Layout

Update your **PI Planning (Qx-20xx)** page to use this layout.

### Section 1: The Commitments (Customer View)
*   **Macro:** `Jira Issues`
*   **Source:** Demand Filter (A)
*   **Key Insight:** This table tells you **"Are we on track to deliver to the customer?"**
*   **Columns:**
    *   `Project` (Customer Name)
    *   `Summary` (The Deliverable)
    *   `Target Release Date`
    *   `Status` (Of the Customer Epic)
    *   **`Linked Issues`** (CRITICAL: This shows the linked `CIM`/`CX` tickets. If this is empty, *work hasn't started*.)

### Section 2: The Execution (Team View)
*   **Macro:** `Jira Issues`
*   **Source:** Supply Filter (B)
*   **Key Insight:** This table tells you **"Who are we building this for?"**
*   **Columns:**
    *   `Key` (e.g., `CIM-505`)
    *   `Summary` (The Feature Name)
    *   `Team`
    *   `Status` (Dev Status)
    *   **`Linked Issues`** (CRITICAL: This shows the `NHCAP`/`MPCP` link. If this is empty, *this feature might not be a customer priority*.)

---

## 3. The "Handshake" Validation (Risk Check)

Use these manual checks or advanced queries to find gaps during the planning meeting.

### Check 1: The "Unfulfilled Promise"
*   **Look at Section 1.**
*   **Identify:** Any row where the `Linked Issues` column is **Empty**.
*   **Meaning:** You have a contract/commitment to `NHCAP` or `MPCP` due this quarter, but **no** tickets have been created in the `CIM` or `CX` backlog to do the work.
*   **Action:** Create a `CIM` ticket immediately and link it.

### Check 2: The "Orphan Feature"
*   **Look at Section 2.**
*   **Identify:** Any Feature where the `Linked Issues` column does **not** point to a Customer Project.
*   **Meaning:** Engineering is building something that is not directly tied to a specific Customer Deliverable.
*   **Action:** Verify if this is "Product Roadmap" work (valid) or "Unnecessary Gold-plating" (invalid).

---

## 4. Implementation Checklist

1.  **Define the Link Type:** Ensure a link type exists in JIRA (e.g., `Implements`).
2.  **Tag Customer Epics:** Go to `NHCAP`, `MPCP`, etc., and ensure their Epics for Q1 have a `Target Release Date` or `FixVersion`.
3.  **Tag Team Features:** Go to `CIM`, `CX`, etc., and ensure their tickets for Q1 have the `Target PI` field set.
4.  **Create the Links:** During the PI Planning session, physically link the `CIM` tickets to the `NHCAP` tickets.
