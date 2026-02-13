# Expertflow Backlog Management & AI-Driven Delivery

## 🚀 Overview
This project defines and implements a high-velocity, AI-augmented development process for the **Expertflow CX** platform. By adapting Scaled Agile Framework (SAFe) principles for smaller teams and integrating AI agents as first-class team members, we aim to eliminate management debt and maximize delivery speed (productivity).

## 🏗️ The "Speed-Native" Architecture
The core of this project is a streamlined 4-level hierarchy designed to move work from strategic conception to production as fast as possible.

### 📊 1. Lean Hierarchy
- **Level 0: Initiative** - Strategic anchors and business themes.
- **Level 1: Epic** - Tactical outcomes deliverable within 1-2 Program Increments (PIs).
- **Level 2: Story / Bug / Task** - The primary units of value and effort.
    - **Story:** New product capabilities.
    - **Bug:** Production/Customer-reported recovery.
    - **Task:** Operational effort (Lab setup, UX, etc.).
- **Level 3: Sub-task / Story-bug** - Technical breakdown and in-development fixes.

### 🚦 2. Dual-Track Workflow
- **Release-Track:** Mandatory QA and release cycles for all product code (Stories/Bugs).
- **Fast-Track:** Simplified execution for operational work (Tasks) that does not impact product code.

### ⛓️ 3. The "Golden Chain" (Prioritization)
We utilize a **Link-Driven Prioritization** model where Customer Commitments (`CUS` projects) are linked as **"IS BLOCKED BY"** Product Deliverables (`INTERNAL` projects). This automatically highlights critical path work in JIRA without the need for manual ranking meetings.

## 🤖 AI-Native Integration
This project utilizes the **BMAD (Breakthrough Method for Agile AI-Driven Development)** framework. AI agents (Analyst, Architect, Developer, etc.) work alongside humans within strict Work-In-Progress (WIP) limits to ensure continuous flow.

## 📁 Repository Structure
- **`_bmad/`**: Contains the BMAD framework configuration, agent definitions, and specialized workflows.
- **`_bmad-output/`**: The vault for all generated analysis, JIRA configuration specs, and architectural blueprints.
- **`project-context.md`**: The "Bible" of the project, containing the finalized standards for hierarchy and execution.

---
*Managed by the Expertflow PMT (Product Management Team).*
