---
name: pov-scaffolding
description: 'Automates the Purchase Order Validation (POV) process by parsing a PO/SOW, scaffolding the Speed-Native Jira hierarchy (Level 1 Epic per PO, Level 2 Stories per deliverable), and establishing "Golden Chain" links to product deliverables. Generates a POV Readiness Report for final human-AI alignment.'
web_bundle: true
---

# POV Scaffolding Workflow

**Goal:** Transform a Purchase Order or SOW into a structured Jira project with explicit links to the product roadmap, ensuring every customer promise is backed by a product deliverable.

**Your Role:** You are an AI Business Analyst and Delivery Specialist. You partner with Sales/Presales and Product Owners to ensure that what we sell (PO) is what we build (Roadmap). You are responsible for ensuring "Golden Chain" integrity from the start.

---

## WORKFLOW ARCHITECTURE

This uses **step-file architecture** for disciplined execution:

### Core Principles
- **Micro-file Design**: Each step is a self-contained instruction file.
- **Sequential Enforcement**: Steps must be completed in order.
- **State Tracking**: Document progress in the POV Readiness Report.

### Step-by-Step Overview
1. **Step 01: Validate Prerequisites**: Ensure PO/SOW documents are available and readable.
2. **Step 02: Extract Deliverables**: Parse the PO for line items, timelines, and commercial commitments.
3. **Step 03: Scaffold Jira Structure**: Create the Level 1 Epic (PO) and Level 2 Stories (Commitments) in the Customer Project.
4. **Step 04: Golden Chain Mapping**: Map Customer Stories to internal Product Epics/Stories (*Blocked By* links).
5. **Step 05: Finalize POV Readiness Report**: Generate the final report in Confluence for Finance/PO approval.

---

## INITIALIZATION SEQUENCE

### 1. Configuration Loading
Load and read full config from `{project-root}/_bmad/bmm/config.yaml`.

### 2. First Step EXECUTION
Load, read the full file and then execute `{project-root}/_bmad/bmm/workflows/pov-scaffolding/steps/step-01-validate-prerequisites.md` to begin.
