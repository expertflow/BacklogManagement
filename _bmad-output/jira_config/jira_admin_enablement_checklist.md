# JIRA Admin Enablement Checklist: "Speed-Native" Backlog
**Target Architecture:** 4-Level Lean Hierarchy + Universal Categorization

## 1. Issue Type Configuration
*   [ ] **Create "Initiative" Issue Type:** Add a new issue type called `Initiative` (Level 0).
*   [ ] **Update Hierarchy Levels:** Ensure `Initiative` is at the top, `Epic` is Level 1, and `Story/Bug/Task` are Level 2.
*   [ ] **Enable Bug at Level 2:** Update the Issue Type Scheme for Product Projects (CIM, CCC, etc.) to allow `Bug` issues to have an `Epic` as a parent.
*   [ ] **Retire "New Feature":** (Optional) Remove or hide the "New Feature" type to prevent confusion with "Story."

## 2. Custom Field Enforcement
*   [ ] **Field:** `Work category` (Found ID: `customfield_10060`).
*   [ ] **Context:** Apply this field to `Initiative`, `Epic`, `Story`, `Bug`, and `Task`.
*   [ ] **Requirement:** Set this field to **Mandatory** on the "Create" and "Edit" screens for all aforementioned types.
*   [ ] **Validation:** (Optional) Add a JIRA Workflow Validator to prevent transitions to "In Progress" if the `Work category` is empty.

## 3. Link Type Verification
*   [ ] **Verify "Blocks" Link:** Ensure the `Blocks / Is Blocked By` link type (ID: 10000) is enabled across all Customer (`CUS`) and Product (`INTERNAL`) projects.
*   [ ] **Cross-Project Linking:** Verify that users have permission to link issues between different projects (e.g., `NHCAP` -> `CIM`).

## 4. Board Configuration (Boards 1310 & 1277)
*   [ ] **Card Colors:** Add a JQL-based color rule to Board 1310 (Product Development):
    *   **Color:** RED (#FF5630)
    *   **JQL:** `issue in linkedIssues("is blocked by", "projectCategory = 'Customer projects'")`
*   [ ] **Quick Filters:** Add a "Customer Blockers" filter:
    *   **JQL:** `issue in linkedIssues("is blocked by")`

## 5. Automation Rules (Global or Project-Specific)
*   [ ] **Auto-Inherit Category:** 
    *   **Trigger:** Issue Created (Level 2).
    *   **Condition:** Parent Epic exists.
    *   **Action:** Set `Work category` to match `Trigger Issue -> Parent -> Work category`.
