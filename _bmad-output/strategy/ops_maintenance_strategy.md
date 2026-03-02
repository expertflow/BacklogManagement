# Operations & Maintenance Workflow Strategy

**Goal:** Eliminate "hidden" operational work and automate the handoff between Finance (Commercial) and DevOps/Support (Technical).

---

## 1. The "Master Ops Calendar" Automation
To ensure commercial renewals translate into technical actions, we use a shared intake trigger.

### 1.1 Finance-to-Jira Trigger
*   **Source:** CRM (Hubspot) or Finance Master Sheet.
*   **Trigger:** Renewal date is `T-30 days`.
*   **Action:** AI Analyst creates a **Level 2 Task** in the relevant `CUS-[Name]` project.
*   **Track:** **Fast-Track** (Does not require a product release).
*   **Priority:** 
    *   `T-30 to T-14`: Medium.
    *   `T-14 to T-0`: High.

### 1.2 Automated Task Scaffolding
Every recurring maintenance task must include a link to the standard operating procedure (SOP):
*   **Work Type:** Security Certificate Update -> *Link to Cert SOP*.
*   **Work Type:** License Key Refresh -> *Link to License SOP*.
*   **Work Type:** Log Cleanup/Health Check -> *Link to Maintenance SOP*.

---

## 2. Production "Hot-Swaps" (P1/P2 Support)
Handling emergency production issues without breaking the Speed-Native flow.

### 2.1 The "Slot Swap" Rule
*   **Trigger:** A P1/P2 Support Ticket is escalated to Engineering.
*   **Action:** A developer (Human or AI) pulls the Bug into an active WIP slot.
*   **The Swap:** The developer must **"Flag"** their current story as `Blocked by Emergency` and move the Bug to `In Progress`.
*   **Impact:** This ensures we maintain the `(H+A) x 1.5` WIP limit even during emergencies.

---

## 3. Maintenance Work Categories (Fast-Track)
The following tasks are strictly **Fast-Track** and should be closed as soon as the manual action is verified:
-   **Environment Configuration:** Lab setups, customer instance hardening.
-   **Access Management:** VPN setup, user credential rotations.
-   **Compliance/Security:** Monthly vulnerability scans, certificate renewals.
-   **Documentation:** Updating project Wikis, creating hand-over docs.

---

## 4. Visibility: The Ops Dashboard
A "Pulse" dashboard in Confluence/Jira showing:
1.  **Upcoming Renewals:** (Next 30 days).
2.  **Active Hot-Swaps:** (Production bugs in progress).
3.  **Fast-Track Velocity:** Number of Ops tasks closed per sprint.
