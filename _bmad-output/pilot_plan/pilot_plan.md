# Pilot Plan: Operation Golden Thread
**Objective:** Validate the "Cross-Project Handshake" hierarchy in a controlled environment before full rollout.

---

## 1. Scope
*   **Target PI:** Q2-2025 (Next Planning Cycle)
*   **Pilot Customer:** Missouri Poison Center (`MPCP`)
*   **Pilot Product Team:** CX Core Team (`CIM`)

## 2. Success Criteria
1.  **Traceability:** Can we click from an `MPCP` Epic to see the exact status of the `CIM` development work?
2.  **Visibility:** Does the new PI Planning Dashboard accurately show "Gaps" (MPCP Epics with no CIM links)?
3.  **Adoption:** Does the Project Manager (PM) for MPCP and the Product Owner (PO) for CIM understand the linking process?

---

## 3. Execution Steps

### Phase 1: Configuration (Days 1-2)
*   **Who:** JIRA Admin / Architect
*   **Actions:**
    1.  Create the JIRA Link Type: `Implements` / `Is Implemented By`.
    2.  Add the `Target PI` field to both `MPCP` and `CIM` projects.
    3.  Create the "PI Planning Dashboard" page in Confluence using the V2 Specification.

### Phase 2: Data Prep (Days 3-5)
*   **Who:** PM (MPCP) & PO (CIM)
*   **Actions:**
    1.  **PM:** Go to the Missouri Poison Center Confluence page.
    2.  **PM:** Create/Update the "Deliverables" table. ensure 3 top priorities for Q2 have JIRA Epics in the `MPCP` project.
    3.  **PO:** Review the `CIM` backlog. Identify the Features/Stories that address these 3 priorities.
    4.  **PO:** Link the `CIM` tickets to the `MPCP` Epics using the `Implements` link type.

### Phase 3: The "Dry Run" (Pre-PI Review)
*   **Who:** Head of Product / Release Train Engineer
*   **Actions:**
    1.  Open the new PI Planning Dashboard.
    2.  **Verify:** Do the 3 MPCP Epics show up in "Section 1"?
    3.  **Verify:** Do they show the linked `CIM` tickets in the "Linked Issues" column?
    4.  **Test the Gap:** Create a dummy "Unplanned Deliverable" in MPCP and confirm it appears on the Risk Board.

### Phase 4: Full PI Planning (The Real Test)
*   **Who:** All Teams
*   **Actions:**
    1.  Use the dashboard as the primary visual aid during the Q2 Planning session.
    2.  Ask the "Golden Question" for every feature: *"Which Customer Deliverable does this implement?"*

---

## 4. Rollout Decision
*   **Go:** If the dashboard successfully highlights gaps and dependencies, proceed to apply this to all top-tier customers (LLA, MCB, etc.) for Q3.
*   **No-Go:** If the overhead of linking is too high or the visibility is confusing, revert to manual mapping and refine the architecture.
