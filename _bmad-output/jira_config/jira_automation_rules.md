# Jira Automation Specification: The Golden Chain Integrity Rule

**Goal:** Automatically identify and flag "Customer Commitments" that are missing a "Product Deliverable" link, preventing "Hidden Work" and missed deadlines.

---

## Rule 1: Flag Missing Golden Chain Links
*   **Trigger:** `Issue Created` OR `Issue Updated`
*   **Scope:** All Projects matching `CUS-*` (Customer Projects)
*   **Conditions:**
    *   `Issue Type` equals `Story` (Level 2 Commitment).
    *   `Status` is NOT `Done` or `Cancelled`.
    *   **Advanced JQL Condition:** 
        `issue NOT IN linkedIssues("is blocked by")` 
        *(Translation: Find stories that do NOT have an inward link of type 'is blocked by')*
*   **Actions:**
    1.  **Label Issue:** Add label `golden-chain-missing`.
    2.  **Set Field:** Set `Priority` to `High` (or `Highest` if the due date is within 14 days).
    3.  **Post Comment:** 
        > "⚠️ **Golden Chain Violation:** This Customer Commitment is not linked to an internal Product Deliverable. Please link this to an Epic or Story in the `EF-INTERNAL` project to ensure prioritization."
    4.  **Flag Card:** Set `Flagged` to `Impediment`.

---

## Rule 2: Automatic Risk Escalation
*   **Trigger:** `Scheduled` (Daily Check)
*   **JQL:** `project in (CUS-*) AND labels = golden-chain-missing AND created < -3d`
*   **Action:** 
    *   **Send Email/Slack Alert:** To the Project Manager and Product Owner.
    *   **Message:** "Customer Commitment [Key] has been unlinked for >3 days. Delivery risk is CRITICAL."

---

## Rule 3: Priority Sync (Inherit Pressure)
*   **Trigger:** `Issue Linked` (Type: *is blocked by*)
*   **Action:** 
    *   If `CUS` issue priority is `Highest`, then set the `EF-INTERNAL` blocking issue priority to `Highest`.
    *   Remove `golden-chain-missing` label from the `CUS` issue.
