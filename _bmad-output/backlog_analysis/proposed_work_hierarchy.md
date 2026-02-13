# Proposed Work Hierarchy & Backlog Standards

## 1. The Lean 4-Level Architecture (Strategic + Execution)
To maximize productivity and minimize "Management Debt," Expertflow CX standardizes on a 4-level architecture where Level 0 provides strategic direction and Levels 1-3 handle delivery.

### Level 0: Initiative (The Strategic Parent)
- **Definition:** The "Why." A high-level strategic container representing a major business theme, customer outcome, or platform milestone.
- **Role:** Acts as the anchor for all downstream work. No Epic should exist without a parent Initiative.
- **Mandatory Metadata:** `Work Category`, `Strategic Priority`.

### Level 1: Epic (The Outcome)
- **Definition:** The "What." A large body of work within an initiative, deliverable within 1-2 Program Increments (PIs).
- **Mandatory Link:** Must link to a Level 0 Initiative.

### Level 2: Story (The Unit of Value)
- **Definition:** The "Unit of Delivery." The smallest independently valuable and testable unit of work.
- **Rules:** 
    - Replaces the "Feature" level.
    - Must fit within a single Sprint.
- **Mandatory Metadata:** `Work Category`.

### Level 3: Sub-task & Story-bug (The Unit of Action)
- **Sub-task:** Technical breakdown of a Story.
- **Story-bug:** A defect identified during the development/QA of a specific Story.
- **Rule:** Story-bugs live at this level to keep the main backlog clean.

---

## 2. Universal Work Categories
Every level (Initiative, Epic, and Story) **MUST** be tagged with one of the following:

| Category | Description |
| :--- | :--- |
| **Business Feature** | New customer-visible capabilities. |
| **Enabler** | Infrastructure/Architecture supporting future features. |
| **Technical Debt** | Stability, performance, or refactoring. |
| **Spike / Investigation** | Research and discovery (Story level only). |

---

## 3. Cross-Project Linking (The Fulfillment Thread)
To bridge the gap between Customer Promises and Product Execution, all customer-driven work must follow a standardized linking protocol between Jira projects.

### The Two-Project Context:
- **Customer Projects (`CUS-XXX`):** Capture "Customer Commitments" (Requirements/Promises).
- **Product Projects (`EF-INTERNAL`):** Capture "Product Deliverables" (Functional/Technical Execution).

### Fulfillment Link Protocol:
Every **Customer Commitment** that requires development must be linked to a **Product Deliverable** using the following specific link type:
- **Link Type:** `Implements / Is Implemented By`
- **Rule:** A Product Story or Epic can fulfill multiple Customer Commitments (One-to-Many).

---

## 4. Productivity Rules (WIP & Flow Management)
1. **Pull System:** New work is only pulled when an item is moved to "Done" and WIP limits allow.
2. **Category Balance:** No more than 30% of a team's WIP should be "Technical Debt" unless explicitly approved for a "Hardening Sprint."
3. **The "Golden Thread":** Any work item without an `Initiative` and `Work Category` is considered "Orphaned" and will be removed from the active backlog.
