# Story: [STORY TITLE]

**Story ID:** STORY-[EPIC_NUMBER].[STORY_NUMBER]
**Epic:** [PARENT EPIC TITLE] (EPIC-[NUMBER])
**Status:** To Do | In Progress | In Review | Done
**Priority:** Must Have | Should Have | Could Have
**Author:** [AUTHOR NAME]
**Date:** [DATE]

---

## 1. User Story

<!-- Follow the standard format. Be specific about the persona, action, and benefit. -->

> **As a** [PERSONA NAME],
> **I want** [SPECIFIC ACTION the user performs],
> **so that** [MEASURABLE BENEFIT or value gained].

<!-- 
Good example:  "As a Solo Developer, I want to drag a task card from 'To Do' to 'In Progress' so that I can visually track my workflow without editing task details."
Bad example:   "As a user, I want to move tasks so that it's easier." (Too vague — who? how? what's easier?)
-->

---

## 2. Acceptance Criteria

<!-- 
Write 3-5 specific, testable conditions. Use Given/When/Then format for clarity.
Each criterion should be independently verifiable — no ambiguity.
-->

- [ ] **AC-1:** Given [PRECONDITION], when [ACTION], then [EXPECTED RESULT].
- [ ] **AC-2:** Given [PRECONDITION], when [ACTION], then [EXPECTED RESULT].
- [ ] **AC-3:** Given [PRECONDITION], when [ACTION], then [EXPECTED RESULT].
- [ ] **AC-4:** Given [PRECONDITION], when [ACTION], then [EXPECTED RESULT].
- [ ] **AC-5:** Given [PRECONDITION], when [ACTION], then [EXPECTED RESULT].

<!-- 
Good AC:  "Given the user is on the board view, when they click the '+ Add Task' button, then a modal appears with title and description fields."
Bad AC:   "Tasks can be added." (Not testable — how? where? what fields?)

Tip: If you can't write clear ACs, the story may be too big. Split it.
-->

---

## 3. Technical Notes

<!-- Optional: Implementation hints, architectural decisions, or constraints. -->

### Suggested Approach
- [e.g., Use React state to manage task data]
- [e.g., Store tasks in localStorage under key 'taskboard-tasks']
- [e.g., Use HTML5 Drag and Drop API or react-beautiful-dnd]

### UI/UX Considerations
- [e.g., Modal should close on Escape key or clicking outside]
- [e.g., Show loading/saving indicator when persisting data]

### Edge Cases to Handle
- [e.g., What happens when localStorage is full?]
- [e.g., What if task title is empty?]
- [e.g., Maximum character limit for task description]

<!-- 
These are hints, not strict requirements. The developer has freedom in implementation.
Only include notes that would prevent common mistakes or save significant time.
-->

---

## 4. Estimation

| Attribute | Value |
|-----------|-------|
| **Story Points** | [1 / 2 / 3 / 5 / 8] |
| **Estimated Duration** | [e.g., 0.5 days / 1 day / 2 days / 3 days] |
| **Complexity** | [Low / Medium / High] |
| **Risk** | [Low / Medium / High] |

<!-- 
Story point guide:
  1 = Trivial change, < 2 hours (e.g., add a button label)
  2 = Small task, half day (e.g., create a static component)
  3 = Medium task, 1 day (e.g., form with validation)
  5 = Larger task, 2 days (e.g., drag & drop implementation)
  8 = Complex task, 3 days (e.g., full CRUD with persistence)
  
If a story is > 8 points, it should be split into smaller stories.
-->

---

## 5. Definition of Done

- [ ] All acceptance criteria are met
- [ ] Code is reviewed (or self-reviewed)
- [ ] No console errors or warnings
- [ ] Works in target browsers
- [ ] Responsive design verified (if applicable)
- [ ] Edge cases handled gracefully

---

<!--
## INVEST Validation Checklist

Use this checklist to validate the quality of this User Story before development:

✅ [I] Independent — Can this story be developed without depending on other stories?
     Ask: "Can a developer pick this up without waiting for another story?"
     
✅ [N] Negotiable — Is there room for discussion on implementation details?
     Ask: "Are we specifying WHAT, not HOW?"

✅ [V] Valuable — Does this story deliver clear value to the end user?
     Ask: "Would a user notice and care if this was missing?"

✅ [E] Estimable — Can we reasonably estimate the effort?
     Ask: "Do we understand enough to give it story points?"

✅ [S] Small — Can this be completed in 1-3 days?
     Ask: "If it takes more than 3 days, should it be split?"

✅ [T] Testable — Can we write specific tests for the acceptance criteria?
     Ask: "Can we demonstrate this works in a review?"

❌ If any check fails, refine the story before starting development.
-->

---

## Revision History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | [DATE] | [AUTHOR] | Initial draft |
