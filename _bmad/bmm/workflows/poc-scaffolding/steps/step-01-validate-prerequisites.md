# Step 01: Validate Prerequisites

**Goal:** Ensure the necessary documents and context are present before generating the PoC Intake RFC.

---

## EXECUTION STEPS

### 1. Document Discovery
- Search for the input discovery files (e.g., PDF, Markdown, or meeting notes) provided by the Sales/Presales team.
- **Requirement:** The input must contain at least the **Customer Name** and a summary of the **Functional Goals**.

### 2. Validation Checks
Verify the following information is extractable:
- **Customer Identity:** (e.g., LLA, STC, Bank of Egypt).
- **Core Problem Statement:** "Why are we doing this PoC?"
- **Estimated Deadline:** When is the demo or "Go-No-Go" date?

### 3. Contextual Retrieval
- Check the **PRS** (Presales) project in Jira for any existing Epics with the same customer name to avoid duplicates.

---

## OUTPUT CRITERIA
1. **Success:** All required metadata is present. **Proceed to Step 02.**
2. **Failure:** Critical information is missing. **Pause and request missing details from the user.**

---

## NEXT STEP
Execute `_bmad/bmm/workflows/poc-scaffolding/steps/step-02-generate-poc-intake-rfc.md`.
