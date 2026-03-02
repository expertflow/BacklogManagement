# Strategic Backlog: Expertflow CX AI-Native Workflows

This document tracks the prioritized "Next Steps" for the BMAD Orchestrator and team to move from strategy to full implementation.

## 1. Feedback Loop Refinement
- [ ] **Automate the "Denominator" (Job Size):** Develop the prompt and logic for the AI Architect to estimate Story Points by scanning existing service codebases (e.g., `whatsapp-connector`, `core-api`).
- [ ] **Formalize "Partner Aggregator" (Loop 3):** Define the "Market Pattern Finder" agent. This includes identifying data sources (Hubspot Meeting Notes, Slack) and the pattern-matching logic for regional/technical trends.
- [ ] **Simulation & Calibration:** Run a test of the AI-Native WSJF formula using real historical feedback. Calibrate the weightings (Usage, Commercial, Strategic, Risk) to ensure the Promotion Threshold (currently 2.5) is accurate.
- [ ] **ZSM Infrastructure Pivot Simulation:** Resume the `correct-course` simulation for the ZSM-290 memory issue to validate the "Resource Bounding" pivot and WIP slot swap logic.

## 2. Missing Workflow Implementation
- [ ] **`poc-scaffolding`:** Implement the full structural definition (steps, logic, templates) for the PoC workflow as defined in the `customer_project_management_strategy.md`.

## 3. Operational Tooling
- [ ] **`ops-maintenance` Trigger:** Define the Jira Automation rules that connect Hubspot Renewal dates to the automated creation of Fast-Track tasks.

---

## 🏁 Session Handover (2026-03-01)

**Current Status:** Strategy updated to reflect Q1-2026 real-time data from PMT Boards 1277 & 1310.

**Key Technical Context:**
*   **Pilot Focus:** ZSM (Zong Smart Messenger) - Infrastructure stabilization and Bitnami migration.
*   **Prioritization Logic:** Formally adopted the **AI-Native WSJF** formula: `[(U*2) + (C/10k) + (S*1.5) + (R*3)] / Story Points`.
*   **Simulation Paused:** Mid-way through a `correct-course` analysis of the **ZSM-290 (Rasa X Memory Freeze)**. This is a "Major Scope" pivot requiring resource bounding (OPS-590).
*   **Workflow Mapping:** Section 7 of `project-context.md` now explicitly defines how PoC -> POV -> Planning -> Pivot workflows connect.

**Next Session Starting Point:** Resume the **ZSM-290 Pivot Simulation** or begin implementing the **`poc-scaffolding`** workflow logic.

---

*Last Updated: 2026-03-01 by BMAD Orchestrator*
