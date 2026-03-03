# Step 02: Generate PoC Intake RFC

**Goal:** Transform the validated discovery data into a structured RFC proposal for stakeholder review.

---

## EXECUTION STEPS

### 1. Template Loading
- Load the **PoC Intake RFC Template** from `_bmad-output/templates/poc_intake_rfc_template.md`.

### 2. Data Synthesis
- **Extract Success Criteria:** Identify 3-5 measurable "Technical Wins" from the discovery document.
- **Identify `poc-hack` Opportunities:** Analyze the requirements for high-complexity items that could be "mocked" or "simulated" to meet the deadline.
- **Estimate Resources:** Use historical PoC data or general SA/Dev complexity to provide a preliminary hour estimate.

### 3. Confluence/Markdown Publication
- Generate the draft RFC.
- **Action:** If Confluence access is available, create a page under the `PRESALES` space. Otherwise, save as a local Markdown file in `_bmad-output/poc_analysis/[Customer]_PoC_RFC.md`.

---

## OUTPUT CRITERIA
1. **Success:** The draft RFC is created and the link/file path is shared with the user.
2. **Failure:** Unable to map requirements to success criteria. **Request clarification.**

---

## NEXT STEP
Execute `_bmad/bmm/workflows/poc-scaffolding/steps/step-03-approval-processing.md`.
