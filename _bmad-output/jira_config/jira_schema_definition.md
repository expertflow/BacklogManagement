# JIRA Schema & Configuration Specification: The Golden Thread

**Purpose:** This document defines the configuration changes required in JIRA to support the alignment of Customer Projects with Product Backlogs.

---

## 1. Issue Types

### A. Level 1: Epic (Existing)
*   **Usage:** Represents a "Customer Deliverable" (from Confluence) or a major "Product Initiative".
*   **Recommendation:** Do not create a new issue type. Use the standard `Epic`.
*   **New Field Requirements:**
    *   **Epic Classification** (Custom Field: Select List):
        *   `Customer Deliverable` (Use this for Customer Project work)
        *   `Product Initiative` (Use this for roadmap features)
        *   `Enabler` (Use this for architectural runway/tech debt)

### B. Level 2: Feature (New / Custom)
*   **Usage:** A distinct, value-add component of an Epic that fits within a single Program Increment (PI).
*   **Type:** Standard Issue Type.
*   **Hierarchy:** Child of `Epic`.
*   **Workflow:** `Funnel` -> `Analysis` -> `Backlog` -> `Implementing` -> `Validating` -> `Done`.

### C. Level 3: Story (Existing)
*   **Usage:** A vertical slice of a Feature deployable in a single Sprint.
*   **Hierarchy:** Linked to `Feature` (via "Parent Link" or "Epic Link" depending on JIRA version/plugins like Advanced Roadmaps).

---

## 2. Custom Fields

| Field Name | Type | Context / Description | Options (Examples) |
| :--- | :--- | :--- | :--- |
| **Target PI** | Select List (Single) | Used on **Epics** and **Features** to assign them to a planning quarter. | `Q1-2025`, `Q2-2025`, `Q3-2025` |
| **Customer** | Select List (Single) | Used on **Epics** (and optionally Features) to filter work by client. | `MCB`, `LLA`, `Missouri Poison Center`, `Expertflow (Internal)` |
| **Confluence Link** | URL Field | Used on **Epics** to provide a direct "Hard Link" back to the specific row in the Customer Page. | *Free Text URL* |
| **Epic Classification**| Select List (Single) | Distinguishes customer work from internal work. | `Customer Deliverable`, `Product Initiative`, `Enabler` |

---

## 3. Issue Linking

### New Link Type: "Delivers"
*   **Purpose:** To create a semantic "Golden Thread" between the Customer Deliverable (Epic) and the Product Work (Feature).
*   **Outward Description:** `Delivers` (e.g., "Feature A **Delivers** Epic B")
*   **Inward Description:** `Is Delivered By` (e.g., "Epic B **Is Delivered By** Feature A")

### Hierarchy Mapping
1.  **Epic** (Customer Deliverable)
    *   *Is Delivered By* $\downarrow$
2.  **Feature** (Product Component)
    *   *Parent Of* $\downarrow$ (Standard JIRA Link)
3.  **Story** (Sprint Task)

---

## 4. Screen Schemes

### Epic Screen
*   **Add:** `Epic Classification`, `Customer`, `Target PI`, `Confluence Link`.
*   **Remove:** Unnecessary fields to keep the view clean for PMs.

### Feature Screen
*   **Add:** `Target PI`, `Customer` (optional - can inherit from Epic via automation).

---

## 5. Automation Rules (Optional but Recommended)

1.  **Inherit Customer:** When a `Feature` is linked to an `Epic`, automatically copy the value of the `Customer` field from the Epic to the Feature.
2.  **Status Rollup:** If all `Features` linked to an `Epic` are `Done`, prompt to close the `Epic`.
