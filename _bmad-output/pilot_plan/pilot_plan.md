# Pilot Plan: Operation Golden Thread (Q1-2026)

**Objective:** Validate the "Cross-Project Handshake" by linking active Customer Commitments on Board 1277 to Product Deliverables on Board 1310.

---

## 1. Scope & Target Projects

- **Target PI:** Q1-2026 (Active)
- **Pilot Customer Projects (Board 1277):**
  - **ZSM (Zong Smart Messenger):** Rasa X stabilization and Bitnami Migration.
  - **ZWA (Zong WFM):** Meta App Onboarding & Calabrio Integration.
- **Pilot Product Teams (Board 1310):**
  - **CX-Core:** Core Messenger & SLA logic.
  - **DevOps:** Infrastructure hardening (Postgres monitoring, Image registry).

## 2. Actionable Success Criteria

1. **Direct Traceability:** Every `Critical` issue on Board 1277 (e.g., **ZSM-292** Bot Down Handling) must be linked as **"IS BLOCKED BY"** a technical story on Board 1310.
2. **Gap Visibility:** The PI Planning Dashboard must highlight "Unlinked" customer requests (e.g., **ZWA-2** Meta Onboarding) that lack an assigned product team.
3. **WIP Alignment:** Product teams on Board 1310 must prioritize work that blocks **ZSM** go-lives.

---

## 3. Immediate Execution Steps

### Phase 1: The "Golden Chain" Mapping (Days 1-2)

- **Who:** AI Analyst / PM
- **Actions:**
  1. Audit **Board 1277** for `In Progress` stories.
  2. For each, identify the blocking technical task on **Board 1310** (e.g., **ZSM-290** Memory Issue blocking **ZSM-295** Migration).
  3. Create the Jira Link: `[1277 Issue] is blocked by [1310 Issue]`.

### Phase 2: Dashboard Implementation (Days 3-5)

- **Who:** JIRA Admin / Architect
- **Actions:**
  1. Update the **PI Planning Dashboard (Confluence)** to filter for Q1-2026 tags.
  2. Configure a "Critical Path" gadget showing all **1277** issues blocked by **1310** work.
  3. Flag any **1310** task that is `In Progress` but does NOT support a **1277** commitment (The "Orphaned Work" check).

### Phase 3: The "Triage Sync" (Bi-Weekly)

- **Who:** PO + Tech Lead + Architect (The Triad)
- **Actions:**
  1. Review the **AI-Native WSJF** scores for new feedback on Board 1277.
  2. Promote high-score items (e.g., **ZSM-294** SLA Delivery Failures) into the active 1310 roadmap.

---

## 4. Pilot Evaluation

- **Metrics:** 
  - **Blocker Resolution Time:** Time from 1277 issue creation to 1310 resolution.
  - **Context Fidelity:** Do developers on Board 1310 understand the customer impact of their technical tasks?

