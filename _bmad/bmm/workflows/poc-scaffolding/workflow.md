---
name: poc-scaffolding
description: 'Automates the initial PoC (Proof of Concept) capture process by parsing discovery notes, generating a PoC Intake RFC for approval, and scaffolding the PRS (Presales) Jira hierarchy.'
web_bundle: true
---

# PoC Scaffolding Workflow

**Goal:** Transform a raw Sales Discovery Document or Customer Requirement into a structured, approved PoC plan in the **PRS** (Presales) project, with explicit `poc-hack` tagging for future debt management.

**Your Role:** You are an AI Solutions Architect and Business Analyst. Your mission is to provide a "Technical Win" proposal that balances customer speed with long-term engineering stability. You are responsible for ensuring every PoC is approved and tracked before resources are spent.

---

## WORKFLOW ARCHITECTURE

This uses **step-file architecture** for disciplined execution:

### Core Principles
- **PRS Project Centrality:** All PoC Epics and Stories are created in the `PRS` project.
- **RFC Approval Gate:** No Jira tickets are created until the `PoC Intake RFC` is reviewed and approved.
- **`poc-hack` Guardrails:** Explicitly identify and tag all "speed over quality" compromises.

### Step-by-Step Overview
1. **Step 01: Validate Prerequisites:** Ensure discovery documents or requirement lists are available.
2. **Step 02: Generate PoC Intake RFC:** Parse the input to create the RFC proposal in Confluence.
3. **Step 03: Approval Processing:** Coordinate the review and sign-off of the RFC.
4. **Step 04: Scaffold PRS Structure:** Create the Level 1 Epic (PoC) and Level 2 Stories (Success Criteria/Spikes) in the `PRS` project.
5. **Step 05: PoC Success Dashboard:** Finalize the tracking dashboard for the technical validation phase.

---

## INITIALIZATION SEQUENCE

### 1. Configuration Loading
Load and read full config from `{project-root}/_bmad/bmm/config.yaml`.

### 2. First Step EXECUTION
Load, read the full file and then execute `{project-root}/_bmad/bmm/workflows/poc-scaffolding/steps/step-01-validate-prerequisites.md` to begin.
