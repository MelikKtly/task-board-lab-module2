# Story: Create Task Form

**Story ID:** STORY-02.01
**Epic:** Task Management (CRUD) (EPIC-02)
**Status:** To Do
**Priority:** Must Have
**Author:** AI Assistant
**Date:** 2026-05-06

---

## 1. User Story

> **As a** Solo Freelancer,
> **I want** to click a button to open a task creation form,
> **so that** I can easily add new tasks to my "To Do" list.

---

## 2. Acceptance Criteria

- [ ] **AC-1:** Given the user is on the main board view, when they click the "+ Add Task" button in a column, then a modal or inline form appears.
- [ ] **AC-2:** Given the form is open, when the user views it, then they see a required "Title" input and an optional "Description" textarea.
- [ ] **AC-3:** Given the user fills out the Title and clicks "Save", then a new task is created and appears at the bottom of the corresponding column.
- [ ] **AC-4:** Given the user clicks "Cancel" or clicks outside the modal, then the form closes without creating a task.
- [ ] **AC-5:** Given the user tries to save without a Title, then the form prevents submission and shows a validation error.

---

## 3. Technical Notes

### Suggested Approach
- Use React state to manage modal visibility and form inputs.
- Create a reusable `TaskForm` component.

### UI/UX Considerations
- Focus should be immediately placed in the Title input when the form opens.
- Pressing Escape should close the form.

---

## 4. Estimation

| Attribute | Value |
|-----------|-------|
| **Story Points** | 3 |
| **Estimated Duration** | 1 day |
| **Complexity** | Medium |
| **Risk** | Low |

---

## 5. Definition of Done

- [ ] All acceptance criteria are met
- [ ] Code is reviewed (or self-reviewed)
- [ ] No console errors or warnings
- [ ] Works in target browsers
- [ ] Responsive design verified (if applicable)
- [ ] Edge cases handled gracefully

---

## Revision History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | 2026-05-06 | AI Assistant | Initial draft |
