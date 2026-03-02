# Project Context: Expertflow CX Backlog Management

## 0. Context Inheritance
This project inherits all strategic vision, work categories, and CI gates defined in the **[Expertflow Global Context](./_bmad/bmm/data/expertflow-global-context.md)**. Local rules defined here override global rules only when explicitly stated.

## 1. Project Overview

**Product:** Expertflow CX (20+ Microservices)  
**Goal:** Establish a high-velocity, AI-augmented development process using a simplified SAFe framework and Team Topologies principles.  
**Core Objective:** Increase delivery speed (Productivity) by eliminating hierarchical confusion and automating strategic alignment.

## 2. The "Speed-Native" Hierarchy (4-Level Architecture)

To minimize management overhead and maximize flow, all work must follow this structure:


| Level       | Issue Type               | Purpose                                | Parent Requirement      |
| ----------- | ------------------------ | -------------------------------------- | ----------------------- |
| **Level 0** | **Initiative**           | Strategic Parent / Business Theme      | None (Top Level)        |
| **Level 1** | **Epic**                 | Major functional or technical outcome  | Must link to Initiative |
| **Level 2** | **Story / Bug / Task**   | **The Unit of Value / Effort.**        | Must link to Epic       |
| **Level 3** | **Sub-task / Story-bug** | The Unit of Action / In-progress Fixes | Must link to Level 2    |


## 2.1 The Two Execution Tracks

To maximize velocity, work follows one of two paths based on its impact on the product codebase:

-   **Release-Track (Stories/Bugs):** Requires the full `Build -> QA -> Release` lifecycle. Changes the core product bits.
-   **Fast-Track (Tasks/Lab/Docs/Ops):** Bypasses the formal release cycle. Changes are marked "Done" upon verification (e.g., updating a customer's security certificate, setting up a lab, or updating a document).

*Note: All **Customer Instance Ops/Admin** tasks follow the Fast-Track.*

## 3. Universal Work Categories

Every Initiative, Epic, and Story **MUST** be tagged with one of these categories to track investment health:

- **Business Feature:** New customer-facing capabilities (Includes **PoC Blockers** and **Strategic Vision**).
- **Customer Feedback:** Requests from live projects or post-production (Includes **Mid-Project Pivots** and **Partner Requests**).
- **Enabler:** Infrastructure, architecture, or R&D supporting future features.
- **Technical Debt:** Stability, performance, or refactoring (Includes **PoC Hacks**).
- **Spike / Investigation:** Research and technical discovery (Story level).
- **Bug / Vulnerability:** Production fixes and security patches.

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

## 7. The Integrated BMAD Workflow Chain

To automate the "Golden Chain," we use a series of connected BMAD workflows that pass context from discovery to operations.

| Workflow Stage | Trigger | Key Input | Primary Output | Connecting "Glue" |
| :--- | :--- | :--- | :--- | :--- |
| **1. PoC Scaffolding** | Presales SOW | Success Criteria | POC Project | `poc-hack` labels |
| **2. POV Scaffolding** | New PO | PoC Project Data | CUS Project | "Golden Chain" Jira Links |
| **3. Project Context** | POV Validation | Jira Backlog | `project-context.md` | Persistent Session Variables |
| **4. Sprint Planning** | Iteration Start | WIP Capacity | Active Sprint | WIP Formula: `(H+A) x 1.5` |
| **5. Correct-Course** | Change Request | Active Plan | Updated Backlog | WIP "Slot Swaps" |
| **6. Maintenance** | CRM Renewal | SOP Library | Fast-Track Tasks | SOP MD Links |

**Constraint:** No workflow may be executed in isolation. Every agent MUST read the `project-context.md` before initiating a task to ensure continuity of the "Golden Thread."

---

*This document serves as the "Bible" for all agents and team members working on Expertflow CX Backlog Management.*