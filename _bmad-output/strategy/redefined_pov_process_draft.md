# Redefined POV (Purchase Order Validation) Process (Draft) - BMAD Augmented

## 1. Current Process Analysis
The current manual process involves:
1. Presales providing the signed Purchase Order (PO) and line-item deliverables.
2. Finance chairing a Purchase Order Validation (POV) meeting.
3. PM reviewing deliverables and identifying risks.
4. Product Owners (POs) planning required development.
5. ProjectDev and PM planning project-specific work.

### Identified Friction Points
- **Synchronous Bottlenecks:** Dependence on high-level meetings for discovery.
- **Manual Discovery:** Risk identification is brain-storming based rather than data-driven.
- **Invisible Dependencies:** Engagement of Product Owners is manual and lacks formal tracking in the "Golden Chain."
- **Lack of Speed-Native Hierarchy:** Work isn't immediately structured into Level 0-3.

## 2. Proposed "POV 2.0" Workflow (AI-Native)

### 2.1 PoC-to-POV Transition (Inheritance)
*Note: PoC (Proof of Concept) is the pre-sales pilot; POV (Purchase Order Validation) is the formal commercial-to-delivery handshake.*

*   **Context Lookup:** The AI Analyst automatically searches Jira for a `POC-[Customer]` project or epics before starting the POV.
*   **Hack Detection:** Any Level 2 stories tagged `poc-hack` in the PoC project are imported into the POV Readiness Report as "High-Risk Technical Debt."
*   **Golden Chain Enforcement:** No POV can be validated if a `poc-hack` exists without a corresponding "Proper Build" Epic in `EF-INTERNAL` (linked via *Blocked By*).
*   **Success Continuity:** Validated Success Criteria from the PoC are carried over as "Mandatory Deliverables" in the POV (Purchase Order Validation).

1. **AI-Led Intake:** AI Analyst parses the PO and generates the **POV Readiness Report** using the **`pov-scaffolding`** BMAD workflow.
2. **The Golden Chain Link:** The Project Manager/Product Owner validates the report and ensures every Customer Story (Commitment) is linked to an internal Product Deliverable via an "Is Blocked By" relationship.
3. **Scaffolding:** The BMAD workflow automatically scaffolds the Level 1 Epic (representing the PO) and Level 2 Stories (representing the commitments) in the Customer Project.
4. **Efficiency Kickoff:** Finance chairs a 15-minute sync for final conflict resolution and commitment, rather than discovery.


## 3. Tooling Strategy
- **BMAD Workflow:** `_bmad/bmm/workflows/pov-scaffolding/workflow.md`
- **Jira:** Project per Customer (e.g., `CUS-LLA`), Epic per PO (Level 1), Stories for Commitments (Level 2).
- **Golden Chain:** "Blocked By" links from Customer Projects to Internal Product Projects.
- **WIP Management:** Team Capacity = (# Humans + # AI Agents) x 1.5.

## 4. Next Steps
- Create a Confluence "POV Readiness Report" Template.
- Define a Jira Automation schema for the "Golden Chain" links.
