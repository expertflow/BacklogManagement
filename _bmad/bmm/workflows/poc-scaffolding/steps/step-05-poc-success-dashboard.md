# Step 05: PoC Success Dashboard

**Goal:** Establish a real-time tracking dashboard for the technical validation phase of the PoC.

---

## EXECUTION STEPS

### 1. Dashboard Creation
- Create a new Confluence page titled **`PoC Success Dashboard: [Customer]`**.
- **Location:** Under the **PoC Intake RFC** page as a child.

### 2. Success Criteria Real-Time Report
- Insert a **Jira Issue/Filter Macro** using the following JQL:
    `project = "PRS" AND labels = "success-criterion" AND labels = "customer-[name]"`
- **Required Columns:** Summary, Status, Assignee, Fix Version, "Metric for Success" (Custom Field if available, otherwise Description snippet).

### 3. Technical Debt Tracking
- Insert a second **Jira Issue/Filter Macro** for **`poc-hack`** tracking:
    `project = "PRS" AND labels = "poc-hack" AND labels = "customer-[name]"`

### 4. Closeout Loop
- Provide a clear **Validation Summary** section for the Solution Architect to fill in upon completion of the demo.

---

## OUTPUT CRITERIA
1. **Dashboard Live:** The link is shared with the Sales and Engineering leads.
2. **Success:** All pre-sales PoC scaffolding is complete. **Workflow Terminated.**
