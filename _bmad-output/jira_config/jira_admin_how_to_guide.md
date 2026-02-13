# Jira Admin How-To Guide: Expertflow Speed-Native Configuration

This guide provides technical instructions for configuring Jira to support the 4-level hierarchy and the dual-track delivery workflow.

---

## 🏗️ 1. Hierarchy & Issue Types
**Goal:** Enable the "Initiative" level and anchor all execution.

### Step 1.1: Enable the "Initiative" Issue Type
1.  Navigate to **Jira Settings > Issues > Issue Types**.
2.  Create a new Issue Type named `Initiative` (Level 0).
3.  Assign it a distinct icon (e.g., a target or trophy).
4.  Add `Initiative` to the **Global Issue Type Scheme** or the specific scheme used by the `PMT` (Product Management) project.

### Step 1.2: Configure Hierarchy Levels
1.  Go to **Jira Settings > Issues > Issue Hierarchy**.
2.  Ensure the levels are mapped as follows:
    *   **Level 0:** `Initiative`
    *   **Level 1:** `Epic`
    *   **Level 2:** `Story`, `Bug`, `Task`
    *   **Level 3:** `Sub-task`, `Story-bug`

### Step 1.3: Enable Epic as Parent for Bugs/Tasks
1.  In your **Issue Type Schemes**, ensure that `Bug` and `Task` are included in the same scheme as `Story` for all development projects (`CIM`, `CCC`, `EAP`).
2.  Verify that the **Parent** field is available on the screens for these issue types.

---

## 💎 2. Custom Fields & Metadata
**Goal:** Enforce mandatory investment tracking.

### Step 2.1: Configure "Work category"
1.  Search for the existing field: `Work category` (Found ID: `customfield_10060`).
2.  **Field Context:** Ensure it is applied to all development projects.
3.  **Options Configuration:** Update the dropdown options to exactly:
    *   `Business Feature`
    *   `Enabler`
    *   `Technical Debt`
    *   `Spike / Investigation`
4.  **Field Configuration:** Set this field to **Required** in the Field Configuration for all `Initiative`, `Epic`, `Story`, `Bug`, and `Task` types.

---

## 🚦 3. Workflow Configuration (Dual-Track)
**Goal:** Distinguish between Released Code and Operational Effort.

### Step 3.1: The "Release-Track" (For Story & Bug)
Ensure the workflow for Stories and Bugs includes the following statuses:
*   `Discovery` ➔ `Refinement` ➔ `Dev-Ready` ➔ `In-Progress` ➔ `QA-Ready` ➔ `In-QA` ➔ `In-Review` ➔ `Release-Ready`.
*   **Constraint:** Transition to `Release-Ready` must require a "QA-Passed" resolution.

### Step 3.2: The "Fast-Track" (For Task)
Apply a simplified workflow to the `Task` issue type:
*   `To Do` ➔ `In Progress` ➔ `Done` (Resolved).
*   *Note:* This allows non-release work (like lab setup) to bypass SQA queues.

---

## ⛓️ 4. Cross-Project Linking (The Golden Chain)
**Goal:** Automate prioritization based on customer impact.

### Step 4.1: Standardize Link Type
1.  Go to **Jira Settings > Issues > Issue Linking**.
2.  Verify the `Blocks` link type exists:
    *   **Outward Description:** `blocks`
    *   **Inward Description:** `is blocked by`

### Step 4.2: Board Visuals (Board 1310)
1.  Open **Board Settings > Card Colors**.
2.  Add a method for "Queries".
3.  Add the following JQL for **RED** highlighting:
    ```sql
    issue in linkedIssues("is blocked by", "projectCategory = 'Customer projects'")
    ```
4.  This will instantly highlight any product story that is blocking a customer commitment.

---

## 🤖 5. Automation Rules
**Goal:** Reduce manual metadata entry.

### Rule: Auto-Inherit Category
*   **Trigger:** When issue is created.
*   **Condition:** `Issue Type` is one of (`Story`, `Bug`, `Task`) AND `Parent` is not empty.
*   **Action:** Edit Issue Field (`Work category`) ➔ Copy value from **Parent**.
