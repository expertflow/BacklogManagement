# Project Context: Expertflow CX Backlog Management

## 1. Project Overview
**Product:** Expertflow CX (20+ Microservices)  
**Goal:** Establish a high-velocity, AI-augmented development process using a simplified SAFe framework and Team Topologies principles.  
**Core Objective:** Increase delivery speed (Productivity) by eliminating hierarchical confusion and automating strategic alignment.

## 2. The "Speed-Native" Hierarchy (4-Level Architecture)
To minimize management overhead and maximize flow, all work must follow this structure:

| Level | Issue Type | Purpose | Parent Requirement |
| :--- | :--- | :--- | :--- |
| **Level 0** | **Initiative** | Strategic Parent / Business Theme | None (Top Level) |
| **Level 1** | **Epic** | Major functional or technical outcome | Must link to Initiative |
| **Level 2** | **Story / Bug / Task** | **The Unit of Value / Effort.** | Must link to Epic |
| **Level 3** | **Sub-task / Story-bug** | The Unit of Action / In-progress Fixes | Must link to Level 2 |

*Note: **Stories/Bugs** follow the 'Release-Track' (Build -> QA -> Release). **Tasks** (Lab Setup, UX, Documentation) follow the 'Fast-Track' (No formal release cycle).*

## 3. Universal Work Categories
Every Initiative, Epic, and Story **MUST** be tagged with one of these categories to track investment health:

- **Business Feature:** New customer-facing capabilities.
- **Enabler:** Infrastructure or architecture supporting future features.
- **Technical Debt:** Stability, performance, or refactoring.
- **Spike / Investigation:** Research and technical discovery (Story level).

## 4. The "Golden Chain" (Cross-Project Linking)
To eliminate prioritization meetings, we use a hard-blocker relationship between customer promises and product execution:

- **Customer Projects (`CUS-XXX`):** Capture "Customer Commitments."
- **Product Projects (`EF-INTERNAL`):** Capture "Product Deliverables."
- **Relationship:** `Customer Commitment` is **BLOCKED BY** `Product Deliverable`.
- **Impact:** Automatically prioritizes internal work based on customer urgency.

## 5. Hybrid Team WIP Management (Human + AI)
We utilize AI Agents as first-class team members. Capacity is managed via strict WIP limits:

- **Team WIP Limit Formula:** `(# of Humans + # of AI Agents) × 1.5` (rounded down).
- **Individual WIP:**
    - **Human Developers:** 1-2 active tasks.
    - **AI Agents:** 2-3 active tasks.
- **The "Review Rule":** AI Agent WIP must not exceed human review capacity. All AI work requires a human "Verification" step before completion.
- **Pull System:** Only start new work when WIP drops below the limit. Prioritize "Finishing over Starting."

## 6. Flow Metrics (Success Criteria)
We measure the health of this system using:
- **Lead Time:** From Customer Request to Production.
- **Cycle Time:** From "In Progress" to "Done."
- **Flow Efficiency:** Ratio of active work time vs. wait time.
- **Blocker Resolution Time:** How long a Product Deliverable blocks a Customer Commitment.

---
*This document serves as the "Bible" for all agents and team members working on Expertflow CX Backlog Management.*
