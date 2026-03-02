# Expertflow CX: AI-Native Business Processes (Target State)

This document defines the formal business processes for the Expertflow CX Backlog Management system. These processes are designed to maintain the "Golden Thread" from initial sales discovery to long-term maintenance.

---

## 1. PoC (Proof of Concept) Process

**Owner:** Presales / Solution Architect
**Objective:** Secure technical "win" while documenting the path to production.

- **Intake:** Customer requirements and success criteria.
- **Execution:** Rapid prototyping, often using `poc-hack` configurations for speed.
- **Outcome:** A validated PoC project with a tagged backlog of "hacks" that must be addressed during the formal project.

## 2. POV (Purchase Order Validation) Process

**Owner:** Finance / Project Manager
**Objective:** The formal "Commercial-to-Delivery" handshake.

- **Intake:** Signed Purchase Order (PO) and Statement of Work (SOW).
- **Transformation:** The `pov-scaffolding` workflow parses the PO, extracts commitments, and inherits `poc-hack` data from the PoC stage.
- **Outcome:** A **POV Readiness Report** and a structured Customer Project (`CUS-XXX`) in Jira with Level 1 Epics and Level 2 Stories.

## 3. The "Golden Chain" Alignment Process

**Owner:** Product Owner (PO) / Architect
**Objective:** Eliminate silos by linking customer revenue to product development.

- **Activity:** PMs and POs perform "Semantic Mapping" to link every Customer Story (Commitment) to an internal Product Story (Deliverable).
- **Rule:** A Customer Commitment is **BLOCKED BY** a Product Deliverable.
- **Outcome:** A unified PI Planning Dashboard that shows exactly how internal engineering work supports specific customer go-lives.

## 4. Hybrid Sprint Planning (H+A Capacity)

**Owner:** Scrum Master / PM
**Objective:** Optimize throughput for a team of humans and AI agents.

- **Activity:** Calculate team bandwidth using the `(Humans + Agents) x 1.5` formula.
- **Constraint:** AI work must always have a human "Reviewer" slot allocated to prevent a backlog of unverified code/docs.
- **Outcome:** An active sprint backlog where work is pulled based on "Finishing over Starting" (Flow Efficiency).

## 5. "Correct-Course" Change Management

**Owner:** Product Owner
**Objective:** Manage mid-project pivots without breaking the WIP limit.

- **Trigger:** A new urgent request or a change in customer priority.
- **Activity:** The "Slot Swap" simulation. To add a new Level 2 Story, an existing Story of equal or greater size must be moved to "Deferred" or "Backlog."
- **Outcome:** A transparent trade-off decision approved by stakeholders, maintaining a stable delivery timeline.

## 6. Fast-Track Maintenance & Operations

**Owner:** Regional DevOps / Finance
**Objective:** Prevent "Maintenance Decay" through automated recurring tasks.

- **Trigger:** CRM renewal date or a security certificate expiry.
- **Execution:** Tasks follow the **Fast-Track** (bypassing the core release cycle).
- **Outcome:** SOPs (Standard Operating Procedures) are executed as documented in the library, ensuring the customer's instance stays secure and updated.

