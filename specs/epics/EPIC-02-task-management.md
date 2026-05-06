# Epic: Task Management (CRUD)

**Epic ID:** EPIC-02
**PRD Reference:** [PRD-task-board.md](../prds/PRD-task-board.md)
**Status:** Draft
**Owner:** Melik Tilla
**Date:** 2026-05-06

---

## 1. Description

Provide the ability for users to create, read, update, and delete tasks within the application. This epic forms the core interactive capability of the board, allowing users to capture their work effectively and manage details.

---

## 2. Primary Persona

- **Name:** Sam, the Side-Project Builder
- **Role:** Full-time developer
- **Key Need Addressed:** A fast, keyboard-friendly way to capture and edit task details without leaving the board view.

---

## 3. Success Criteria

| # | Criteria | Metric | Target |
|---|----------|--------|--------|
| SC-1 | Users can capture new tasks | Task creation success rate | 100% |
| SC-2 | Task creation is fast | Time to create task | < 10 seconds |
| SC-3 | Users can safely delete tasks | Deletion confirmation | 100% of deletions are confirmed |

---

## 4. Scope & Complexity

### Complexity Estimate
- **Size:** M
- **Estimated Duration:** 2 weeks
- **Estimated Story Count:** 5-7 stories

### What's Included
- Task creation modal/form
- Task detail view & editing capability
- Task deletion with confirmation prompt
- `n` keyboard shortcut for new tasks
- Task card UI component

### What's NOT Included
- Moving tasks between columns via drag and drop
- Long-term data persistence (localStorage will be wired fully in EPIC-03, though basic state is needed here)

---

## 5. Dependencies

### Technical Dependencies
- [x] React state management approach defined

### Epic Dependencies
- [x] EPIC-01 (Core Task Board UI) must be completed to have a place to put tasks

### External Dependencies
- [x] None

---

## 6. User Stories

| Story ID | Title | Status | Priority |
|----------|-------|--------|----------|
| STORY-02.01 | Create Task Form | To Do | Must Have |
| STORY-02.02 | View Task Details | To Do | Must Have |
| STORY-02.03 | Edit Existing Task | To Do | Must Have |
| STORY-02.04 | Delete Task with Confirmation | To Do | Must Have |
| STORY-02.05 | Keyboard Shortcut for New Task | To Do | Should Have |

---

## Revision History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | 2026-05-06 | AI Assistant | Initial draft |
