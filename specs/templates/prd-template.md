# PRD: [PROJECT NAME]

**Version:** [VERSION NUMBER]
**Author:** [AUTHOR NAME]
**Date:** [DATE]
**Status:** Draft | In Review | Approved

---

## 1. Overview

### Purpose
<!-- Why does this project exist? What problem are we solving? -->
[Describe the purpose of this product/feature in 2-3 sentences.]

### Problem Statement
<!-- Be specific. Include numbers and data where possible. -->
[Describe the specific problem users face. Quantify the impact — e.g., "Developers spend X hours/week managing tasks across Y disconnected tools."]

### Goals
<!-- What does success look like at a high level? -->
- **Goal 1:** [PRIMARY GOAL — e.g., Reduce task management overhead by X%]
- **Goal 2:** [SECONDARY GOAL]
- **Goal 3:** [TERTIARY GOAL]

---

## 2. User Personas

### Persona 1: [PERSONA NAME]
- **Role:** [e.g., Solo Developer, Team Lead, Freelancer]
- **Background:** [Brief context about who they are]
- **Pain Points:**
  - [Pain point 1 — be specific]
  - [Pain point 2]
- **Needs:** [What they need from this product]
- **Tech Comfort:** [Low / Medium / High]

### Persona 2: [PERSONA NAME]
- **Role:** [ROLE]
- **Background:** [BACKGROUND]
- **Pain Points:**
  - [Pain point 1]
  - [Pain point 2]
- **Needs:** [NEEDS]
- **Tech Comfort:** [Low / Medium / High]

<!-- Add more personas as needed. Aim for 2-3 primary personas. -->

---

## 3. Use Cases

### UC-1: [USE CASE TITLE]
- **Actor:** [Which persona]
- **Precondition:** [What must be true before this scenario]
- **Flow:**
  1. [Step 1]
  2. [Step 2]
  3. [Step 3]
- **Expected Outcome:** [What happens when completed successfully]

### UC-2: [USE CASE TITLE]
- **Actor:** [Which persona]
- **Precondition:** [PRECONDITION]
- **Flow:**
  1. [Step 1]
  2. [Step 2]
  3. [Step 3]
- **Expected Outcome:** [OUTCOME]

### UC-3: [USE CASE TITLE]
- **Actor:** [Which persona]
- **Precondition:** [PRECONDITION]
- **Flow:**
  1. [Step 1]
  2. [Step 2]
  3. [Step 3]
- **Expected Outcome:** [OUTCOME]

<!-- Common mistake: Writing vague use cases. Each step should be a concrete user action. -->

---

## 4. Functional Requirements

<!-- What the system MUST do. Each requirement should be testable. -->

| ID | Requirement | Priority | Notes |
|----|-------------|----------|-------|
| FR-1 | [The system shall...] | Must Have | [NOTES] |
| FR-2 | [The system shall...] | Must Have | [NOTES] |
| FR-3 | [The system shall...] | Should Have | [NOTES] |
| FR-4 | [The system shall...] | Could Have | [NOTES] |
| FR-5 | [The system shall...] | Could Have | [NOTES] |

<!-- Priority levels: Must Have / Should Have / Could Have / Won't Have (MoSCoW) -->
<!-- Tip: "Must Have" items define your MVP. Be strict — fewer is better. -->

---

## 5. Non-Functional Requirements

### Performance
- [e.g., Page load time under X seconds]
- [e.g., UI interactions respond within X ms]

### Security
- [e.g., Data stored securely in localStorage with no PII exposure]
- [e.g., Input sanitization for all user-entered content]

### Accessibility
- [e.g., WCAG 2.1 AA compliance]
- [e.g., Keyboard navigation support]

### Browser Compatibility
- [e.g., Chrome, Firefox, Safari, Edge — latest 2 versions]

### Data Persistence
- [e.g., Data survives browser refresh, stored locally]

<!-- Common mistake: Ignoring non-functional requirements. They define quality. -->

---

## 6. Success Metrics

<!-- Use SMART metrics: Specific, Measurable, Achievable, Relevant, Time-bound -->

| Metric | Target | How to Measure | Timeline |
|--------|--------|----------------|----------|
| [e.g., Task creation time] | [e.g., < 5 seconds] | [e.g., User testing] | [e.g., At launch] |
| [e.g., User retention] | [e.g., 70% weekly return] | [e.g., Analytics] | [e.g., 30 days post-launch] |
| [e.g., Feature adoption] | [e.g., 80% use drag & drop] | [e.g., Usage tracking] | [e.g., 2 weeks post-launch] |

<!-- 
Good metric example:  "80% of users can create a task in under 10 seconds"
Bad metric example:   "Users find the app easy to use" (not measurable!)
-->

---

## 7. Scope

### In Scope (v1.0)
- [Feature/capability 1]
- [Feature/capability 2]
- [Feature/capability 3]

### Out of Scope (future versions)
- [Feature explicitly NOT included and why]
- [Feature deferred to v2]
- [Feature that requires backend — not in this version]

### Assumptions
- [e.g., Users have modern browsers with JavaScript enabled]
- [e.g., No backend or API integration needed for v1]

### Constraints
- [e.g., Must work offline — no server dependency]
- [e.g., Budget/time limitations]

<!-- Be explicit about what's OUT. This prevents scope creep. -->

---

## Appendix

### References
- [Link to related documents, research, competitor analysis]

### Revision History
| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | [DATE] | [AUTHOR] | Initial draft |