# Step 04: Scaffold PRS Structure

**Goal:** Create the approved PoC hierarchy in the **PRS** (Presales) project in Jira.

---

## EXECUTION STEPS

### 1. PRS Epic Creation
- Create a **Level 1 Epic** in the `PRS` project.
- **Summary Format:** `PoC: [Customer Name] - [Summary of Goal]`
- **Description:** Link back to the **PoC Intake RFC** in Confluence.

### 2. Success Criteria Story Creation
- For each Success Criterion in the RFC, create a **Level 2 Story/Spike**.
- **Requirement:** Assign these stories to the PRS Epic.
- **Labels:**
    - `customer-[name]` (mandatory)
    - `poc-hack` (if identified as a hack in the RFC)
    - `success-criterion` (for tracking in the dashboard)

### 3. Acceptance Criteria Extraction
- Map the "Metric for Success" from the RFC into the **Acceptance Criteria** field of the Jira stories.

---

## OUTPUT CRITERIA
1. **Success:** All Jira entities are created and properly linked. **Proceed to Step 05.**
2. **Failure:** Unable to create items in the `PRS` project. **Check permissions.**

---

## NEXT STEP
Execute `_bmad/bmm/workflows/poc-scaffolding/steps/step-05-poc-success-dashboard.md`.
