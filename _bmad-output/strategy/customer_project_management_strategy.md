# Customer Project Management Strategy: Expertflow CX (AI-Native)

## 1. Unified Intake Framework
Customer projects are initiated via two primary triggers, each with a specialized AI-scaffolding workflow.

### A. Purchase Order (PO) - Workflow: `pov-scaffolding`
- **Objective:** Transform a signed PO/SOW into a structured delivery project.
- **Process:** AI parses the PO -> Scaffolds Level 1 Epic (PO) -> Scaffolds Level 2 Stories (Commitments).
- **Outcome:** POV Readiness Report for Finance/PM approval.

### B. Proof-of-Concept (PoC) - Workflow: `poc-scaffolding` (TBD)
- **Objective:** Rapidly deliver specific features to prove value and secure a sale.
- **Process:** AI extracts Success Criteria -> Scaffolds Level 1 Epic (PoC) -> Scaffolds Level 2 Stories (mostly Spikes/Investigations).
- **Outcome:** PoC Success Dashboard in Confluence.

## 2. The "Golden Chain" Alignment
To ensure product-market fit and eliminate prioritization manual overhead:
- **Rule:** Every **Customer Story** (Commitment) in a `CUS` project **MUST** be linked to a **Product Deliverable** in the `EF-INTERNAL` project.
- **Link Type:** `Customer Story` **IS BLOCKED BY** `Product Deliverable`.
- **Visibility:** High-impact product features are automatically prioritized based on their "Customer Blocking" count.

## 3. Speed-Native Hierarchy (4-Level Architecture)
| Level | Issue Type | Definition |
| :--- | :--- | :--- |
| **Level 0** | **Initiative** | High-level Client Journey (e.g., "Digital Transformation 2026"). |
| **Level 1** | **Epic** | The legal/commercial boundary (e.g., "PO-456"). |
| **Level 2** | **Story/Task** | The unit of value (e.g., "Configure WhatsApp integration"). |
| **Level 3** | **Sub-task** | The unit of action (e.g., "Review API response schema"). |

## 4. Hybrid Resource Management
- **Teams:** Stream-aligned (Solutions) Teams own the end-to-end delivery.
- **Capacity:** Calculated as `(Humans + AI Agents) * 1.5`.
- **Role Split:**
    - **Humans:** Focus on complex logic, stakeholder alignment, and "Release-Track" stories.
    - **AI Agents:** Focus on "Fast-Track" tasks (Docs, Tests, Lab Setup, Research).
- **Review Loop:** AI work is always "Blocked By" a human verification step.

## 5. Metrics for Success
- **Lead Time:** From PO Received to Project Sign-off.
- **Wait Time:** Time spent waiting for internal product deliverables (Golden Chain friction).
- **PoC Conversion Rate:** Ratio of PoCs that lead to a PO.
- **AI Efficiency:** % of "Fast-Track" tasks completed autonomously by AI agents.
