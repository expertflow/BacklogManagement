# Step 02: Extract POV Deliverables

**Goal:** Deep-dive parse the PO/SOW to identify individual deliverables, target dates, and commercial commitments.

---

## 1. EXTRACTION PROTOCOL
Parse the source document for:
- **Commercial Commitments:** Specific features, services, or outcomes.
- **Target Dates:** Milestones (Go-live, UAT, Phase 1, etc.).
- **Commercial Metadata:** Total project value, licensing, and partner details.
- **PoC Context Mapping:** Identify which PO deliverables were already addressed (or hacked) during the PoC.

---

## 2. OUTPUT GENERATION
Generate a table summarizing the extracted line items:

| Deliverable (Customer Story) | Target Date | PoC Status | Category |
| :--- | :--- | :--- | :--- |
| [Feature A] | [YYYY-MM-DD] | [Validated/Hacked/New] | [Business Feature/Enabler/Debt] |

---

## 3. NEXT STEPS
1. Present the extracted table to the user for validation.
2. Once validated, proceed to **Step 03: Scaffold Jira Structure**.
