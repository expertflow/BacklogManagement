# Definitive Requirements Analysis & Gap Assessment

### 1. Executive Summary
**Goal:** Establish a structured, reliable mechanism to align **Development Priorities** (Team Backlogs/PI Plans) with **Customer Deliverables** (Customer Projects).
**Methodology:** Scaled Agile Framework (SAFe).
**Current Pain Point:** Disconnect between "What we promised the customer" (Customer Space) and "What we are building" (EF Internal Space/JIRA), leading to prioritization conflicts and risk of missed deliverables.

---

### 2. The "As-Is" State
Your organization currently operates in three distinct, somewhat siloed domains:

#### A. The Customer Domain (Space: `CUS`)
*   **Purpose:** Tracks customer specific projects, environments, and requirements.
*   **Status:** Inconsistent.
    *   **Gold Standard:** Pages like *LLA HybridChat* (ID 1999473) contain excellent tables linking "Feature Requests" directly to JIRA tickets and tracking "Development Phases."
    *   **Reality:** Many recent pages lack this structure, making it impossible to query the aggregate status of "All Customer Promises."
*   **Gap:** No standardized machine-readable format to extract "What is due when?" across all customers.

#### B. The Strategic Planning Domain (Space: `EF Internal`, Page: `PI Planning`)
*   **Purpose:** Program Increment (PI) planning for cross-team alignment (SAFe).
*   **Status:** Strong Process, Weak Input linkage.
    *   Your PI Planning pages (e.g., Q1-2025) are detailed and link efficiently to JIRA for execution.
    *   **Critical Weakness:** The "Customer Deliverables" section relies on external links (Aha!) or loose references. There is no direct, "hard" link between a PI Objective and a specific Customer Project page in Confluence.

#### C. The Execution Domain (Space: `EF Internal`, Page: `Team Backlogs` + JIRA)
*   **Purpose:** Daily execution by teams (CX Core, Voice, etc.).
*   **Status:** Functional but Isolated.
    *   Teams define their work in JIRA Stories/Tasks effectively.
    *   **Blind Spot:** A developer working on a Story often cannot easily see *which* customer needs this feature or *why* it is urgent. Prioritization relies on manual intervention rather than structural visibility.

---

### 3. The Core Problem: "The Product vs. Project Tension"
You are building a **Product** (Expertflow CX), but you are driven by **Projects** (Customer Deployments).

*   **The Conflict:** Customers pay for "Projects" (Deliverables), but Teams build "Product Features" (Capabilities).
*   **The Risk:** A generic "Feature A" might be deprioritized by a Product Owner thinking it's low value, not realizing that "Customer X" has a go-live dependency on it next week.
*   **Root Cause:** The mapping of `Customer Deliverable (Project)` $\to$ `Product Feature (Backlog)` is currently manual, mental, or buried in meeting notes, rather than being a structural link in JIRA/Confluence.

---

### 4. Strategic Recommendations (The "To-Be" Architecture)

To fix this, we must shift from loose associations to **Hard Links**.

#### Recommendation 1: The "Customer Deliverable" Object
We must formalize "Customer Deliverable" as a trackable entity.
*   **Action:** Enforce a strict template in the `CUS` space. Every customer page MUST have a "Deliverables" table.
*   **Requirement:** Every row in this table must have a JIRA Epic link.

#### Recommendation 2: The "Speed-First" Hierarchy (4-Level Architecture)
To eliminate "Management Debt" and increase delivery speed, we are collapsing the complex SAFe hierarchy into a lean, 4-level model:

1.  **Level 0: Initiative (Strategic Parent):** The anchor for all work. Every Epic must link to an Initiative.
2.  **Level 1: Epic (Outcome):** Major functional or technical themes deliverable within 1-2 PIs.
3.  **Level 2: Story (Value):** The unit of execution. Replaces "Features" and "Stories" as separate levels.
4.  **Level 3: Sub-task / Story-bug (Action):** Execution-level details and in-progress fixes.

#### Recommendation 3: Universal Work Categories
To ensure structural visibility of our "Investment Mix," every Initiative, Epic, and Story must be tagged with a **Work Category**:
*   **Business Feature:** Customer-facing value.
*   **Enabler:** Platform/Infrastructure capabilities.
*   **Technical Debt:** Stability and performance.
*   **Spike:** Research and discovery.

**Productivity Impact:** This structure eliminates the need for manual prioritization meetings by allowing "Strategic Priority" to flow automatically from Level 0 to Level 2.

---

### 5. Detailed Findings (From Initial Deep Dive)

#### Customer Project Pages ("CUS" Space)
*   **Good Examples:** "LLA HybridChat" and "Missouri Poison Center" follow a clear template with `Project Summary`, `Customer Environment`, `Development Phases`, and `Feature Requests` linked to JIRA.
*   **Recent Pages:** Inconsistent usage of templates makes automated aggregation impossible.

#### PI Planning Pages
*   **Structure:** "PI Plan (Q1-2025)" follows standard SAFe formats (`PI Objectives`, `Epics Under Consideration`).
*   **Integration:** Heavily integrated with JIRA for execution, but lacks hard links to Confluence Customer pages.

#### Team Backlog Pages
*   **Source of Truth:** Confluence acts as a summary; JIRA is the real engine.
*   **Cadence:** Aligned with Quarterly PI planning.
