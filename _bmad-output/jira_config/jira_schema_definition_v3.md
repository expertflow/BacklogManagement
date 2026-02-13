# JIRA Schema & Configuration Specification V3: Speed-Native Architecture

**Purpose:** This document defines the technical configuration required to implement the lean 4-level hierarchy and the "Blocked By" prioritization engine.

---

## 1. Issue Type Hierarchy (4-Level Architecture)

To minimize management debt, the system is configured into four execution levels:

| Level | Issue Type | Primary Project | Parent Relationship |
| :--- | :--- | :--- | :--- |
| **Level 0** | **Initiative** | `PMT` (Product Management) | None (Strategic Anchor) |
| **Level 1** | **Epic** | `CIM`, `CCC`, `EAP`, etc. | Parent: `Initiative` |
| **Level 2** | **Story / Bug / Task** | `CIM`, `CCC`, `EAP`, etc. | Parent: `Epic` |
| **Level 3** | **Sub-task / Story-bug** | Internal Development | Parent: `Level 2 Item` |

*Note: Level 2 items are split by workflow track: Release-Track (Story/Bug) and Fast-Track (Task).*

---

## 2. Universal Custom Fields

### A. Work Category (`customfield_10060`)
*   **Context:** Mandatory for Initiative, Epic, and Story.
*   **Options:**
    *   `Business Feature`: Customer value enhancement.
    *   `Enabler`: Architectural/Infrastructure work.
    *   `Technical Debt`: Stability, performance, refactoring.
    *   `Spike / Investigation`: Discovery and research.

### B. Strategic Priority
*   **Context:** Initiative Level.
*   **Impact:** Flows down to Epics and Stories via automation or visual highlighting.

---

## 3. The "Golden Chain" Protocol (Cross-Project Linking)

Instead of Parent-Child (which requires issues to live in the same hierarchy), we use **Link-Based Prioritization** to connect Demand (Customer) to Supply (Product).

*   **Link Type:** `is blocked by / blocks` (ID: 10000)
*   **The Protocol:**
    1.  **Customer Commitment** created in `CUS-XXX` Project.
    2.  Linked as **"IS BLOCKED BY"** a **Product Story/Epic** in an internal project.
*   **Visibility:** Boards in `CUS` projects must show the status of the blocking internal issues.

---

## 4. Board Configuration & Visual Cues

### Product Board (e.g., 1310)
*   **Card Colors:** Use JQL to highlight items that are "Blocking" a Customer project issue.
    *   `color: RED` if `issue in linkedIssues("is blocked by", "project in (NHCAP, MPCP, etc)")`
*   **Quick Filters:**
    *   `Blocking Customer`: `issue in linkedIssues("is blocked by")`
    *   `Technical Debt`: `"Work category" = "Technical Debt"`

---

## 5. Required Automations

1.  **Inherit Category:** When a Story is created under an Epic, automatically set the Story's `Work category` to match the Parent Epic.
2.  **Escalate Priority:** If a Product issue is linked to a "Blocker" for a Customer issue with a `Due Date` < 14 days, increase Product issue priority to `Highest`.
3.  **Sync Story-bugs:** When a `Story-bug` (Level 3) is created, automatically update the Parent Story status to "In Progress" (if blocked) or flag it for review.

---

## 6. Implementation Status (Gap Remediation)
- [ ] Create/Enable **Initiative** Issue Type.
- [ ] Set **Work Category** field to "Required" on all applicable screens.
- [ ] Update card color settings on Board 1310 to highlight customer blockers.
