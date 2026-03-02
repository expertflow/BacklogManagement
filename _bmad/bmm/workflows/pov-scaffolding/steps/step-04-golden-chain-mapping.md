# Step 04: Golden Chain Mapping

**Goal:** Establish structural links between Customer Stories (the *what*) and internal Product Deliverables (the *how*).

---

## 1. MAPPING PROTOCOL
For each Customer Story (Commitment) created in Step 03:
1. **Search Product Roadmap:** Look for existing Epics or Stories in `EF-INTERNAL` or other product projects that address the requirement.
2. **Identify Gaps:** If no matching product deliverable exists, tag as `New Development Required`.
3. **Establish Links:** For existing deliverables, create an **"is blocked by"** link from the Customer Story to the Product Deliverable.
    - **Link Type:** `is blocked by`
    - **Inward Link:** `blocks`

---

## 2. OUTPUT GENERATION
Generate a mapping table for the POV Readiness Report:

| Customer Story | Product Deliverable (Jira Key) | Relationship | Status |
| :--- | :--- | :--- | :--- |
| [Feature A] | [EF-PROD-123] | `is blocked by` | Linked ✅ |
| [Feature B] | [TBD - New Dev] | `New Development` | **Gap 🔴** |

---

## 3. NEXT STEPS
1. Present the mapping table to the user for validation and gap identification.
2. Proceed to **Step 05: Finalize POV Readiness Report**.
