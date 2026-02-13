# JIRA Schema & Configuration Specification V2: The Cross-Project Handshake

**Purpose:** This document defines the configuration required to support the "Golden Thread" using native **Parent-Child** relationships between **Customer Projects** (Demand) and **Product Projects** (Supply).

---

## 1. Project Roles & Issue Types

### A. Customer Projects (e.g., `NHCAP`, `MPCP`)
*   **Role:** Tracks customer commitments and UAT.
*   **Primary Issue Type:** `Epic`.
*   **Hierarchy Level:** Level 1 (Parent).

### B. Product Projects (e.g., `CIM`, `CX`, `Voice`)
*   **Role:** Tracks actual engineering development.
*   **Issue Types:** `New Feature` (Level 2) and `Story` (Level 3).
*   **Usage:** New Features are children of Customer Epics; Stories are children of New Features.

---

## 2. The "Golden Thread" Relationship

Instead of using issue links, we utilize the native JIRA **Parent** field to create a strict hierarchy.

*   **Relationship:** `Parent` $\leftrightarrow$ `Child`.
*   **Mapping:**
    *   `Customer Epic` is the **Parent** of `Product New Feature`.
    *   `Product New Feature` is the **Parent** of `Product Story`.

---

## 3. Custom Fields

| Field Name | Type | Context | Project Type |
| :--- | :--- | :--- | :--- |
| **Target PI** | Select List | e.g., `Q1-2025`, `Q2-2025`. | Both |
| **Confluence Link** | URL Field | Link to the specific Customer Project page in Confluence. | Customer Project (Epics) |
| **Work Category** | Select List | Tagging for `Tech Debt`, `Feature`, `Stability`, etc. | Product Project |

---

## 4. Hierarchy Mapping (The Parental Handshake)

1.  **[Customer Project] Epic** (e.g., `NHCAP-24`)
    *   *Role:* Top-level Parent.
    *   *Roll-up:* Progress automatically rolls up from children.
2.  **[Product Project] New Feature** (e.g., `CIM-101`)
    *   *Parent:* `NHCAP-24`.
    *   *Role:* Level 2 Child / Intermediate Parent.
3.  **[Product Project] Story** (e.g., `CIM-505`)
    *   *Parent:* `CIM-101`.
    *   *Role:* Level 3 Child (Leaf node).

---

## 5. Automation Rules

1.  **Parent Status Sync:** When a `New Feature` is moved to `In Progress`, automatically move the Parent `Epic` to `In Progress` (if not already there).
2.  **Progress Notification:** When all children (`New Features`) of a Customer `Epic` are `Done`, notify the Project Manager that the deliverable is ready for UAT.

---

## 6. Screen Schemes

### Customer Project (Epic Screen)
*   **Required Fields:** `Summary`, `Description`, `Target PI`, `Confluence Link`, `Child Issues` (visible).

### Product Project (New Feature/Story Screen)
*   **Required Fields:** `Summary`, `Description`, `Target PI`, `Work Category`, `Parent` (visible).
