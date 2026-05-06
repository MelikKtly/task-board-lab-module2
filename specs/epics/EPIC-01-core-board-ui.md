# Epic: Core Task Board UI & Layout

**Epic ID:** EPIC-01
**PRD Reference:** [PRD-task-board.md](../prds/PRD-task-board.md)
**Status:** Draft
**Owner:** Melik Tilla
**Date:** 2026-05-06

---

## 1. Description

Deliver the core structural layout for the Kanban task board, establishing the three primary columns ("To Do", "In Progress", "Done") and the overall responsive design. This provides the foundational visual canvas where users will track their work.

---

## 2. Primary Persona

- **Name:** Alex, the Solo Freelancer
- **Role:** Freelance full-stack developer
- **Key Need Addressed:** A single-page board that shows all tasks at a glance without complex setup.

---

## 3. Success Criteria

| # | Criteria | Metric | Target |
|---|----------|--------|--------|
| SC-1 | Board renders 3 columns correctly | Visual Layout | 3 fixed columns always visible |
| SC-2 | Responsive on desktop screens | Minimum width support | Fully functional at 768px+ |
| SC-3 | Fast initial load | Render time | < 2 seconds |

---

## 4. Scope & Complexity

### Complexity Estimate
- **Size:** S
- **Estimated Duration:** 1 sprint
- **Estimated Story Count:** 2-3 stories

### What's Included
- Base application layout (Header, Board area)
- Three fixed columns (To Do, In Progress, Done)
- Column counters (initially 0)
- Styling and CSS architecture (Vanilla CSS)

### What's NOT Included
- Actual task cards (handled in EPIC-02)
- Drag and drop functionality (handled in EPIC-03)
- LocalStorage persistence (handled in EPIC-03)

---

## 5. Dependencies

### Technical Dependencies
- [x] Project scaffolding and build setup must be complete (React + Vite)
- [x] TypeScript configured

### Epic Dependencies
- [x] No dependencies — can start independently

### External Dependencies
- [x] No external APIs required

---

## 6. User Stories

| Story ID | Title | Status | Priority |
|----------|-------|--------|----------|
| STORY-01.01 | Implement base layout and CSS | To Do | Must Have |
| STORY-01.02 | Create 3-column Kanban board | To Do | Must Have |

---

## Revision History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | 2026-05-06 | AI Assistant | Initial draft |
