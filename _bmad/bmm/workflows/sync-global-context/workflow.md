---
name: sync-global-context
description: 'Synchronizes the local project context with the Expertflow Global Context (The Company Bible) to ensure alignment with strategic vision and technical mandates.'
---

# Sync Global Context Workflow

**Goal:** Ensure this repository is not operating in a silo. Fetch the latest strategic directives, work categories, and CI gates from the central Expertflow context.

---

## 1. PRE-SYNC CHECK
- [ ] Verify access to the `EF` and `kb` Confluence spaces.
- [ ] Read the current `_bmad/bmm/data/expertflow-global-context.md`.

---

## 2. EXECUTION STEPS
1. **Fetch Latest:** Scan Confluence for updates to "Vision," "Initiatives," and "SAFe-lite Guidelines."
2. **Review Deltas:** Identify changes in universal work categories or CI gates.
3. **Update Global File:** Refresh `_bmad/bmm/data/expertflow-global-context.md`.
4. **Align Local Context:** Update `project-context.md` if local rules conflict with new global mandates.

---

## 3. VALIDATION
- [ ] AI Agent re-reads `project-context.md` to confirm updated "Investment Health" categories.
