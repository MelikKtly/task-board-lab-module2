# Story: Keyboard Shortcut for New Task

**Story ID:** STORY-02.05
**Epic:** Task Management (CRUD) (EPIC-02)
**Status:** To Do
**Priority:** Should Have
**Author:** AI Assistant
**Date:** 2026-05-06

---

## 1. User Story

> **As a** Solo Freelancer,
> **I want** to press the 'n' key to open the new task form,
> **so that** I can capture thoughts instantly without using the mouse.

---

## 2. Acceptance Criteria

- [ ] **AC-1:** Given the user is on the board and not currently typing in an input field, when they press 'n', then the new task modal opens.
- [ ] **AC-2:** Given the modal opens via shortcut, when it appears, then focus is automatically set to the Title input field.
- [ ] **AC-3:** Given the user is typing in a form field (e.g., title or description), when they press 'n', then the character 'n' is typed and the modal does not open again.

---

## 3. Technical Notes

### Suggested Approach
- Attach an event listener to `window` or `document` for `keydown` events.
- Check `document.activeElement` to ensure the user isn't currently inside an `input` or `textarea` before triggering the action.

### UI/UX Considerations
- Ensure accessibility: keyboard shortcut should not conflict with screen reader shortcuts.

---

## 4. Estimation

| Attribute | Value |
|-----------|-------|
| **Story Points** | 2 |
| **Estimated Duration** | 0.5 days |
| **Complexity** | Low |
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
