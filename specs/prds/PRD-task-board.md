# PRD: Personal Task Board

**Version:** 1.0
**Author:** Melik Tilla
**Date:** 2026-05-05
**Status:** Draft

---

## 1. Overview

### Purpose
Build a lightweight, browser-based Kanban task board that enables solo developers to organize and track tasks across multiple projects without relying on heavy project management tools like Jira, Asana, or Trello.

### Problem Statement
Solo developers and freelancers managing 2-3 concurrent projects spend an estimated 25-40 minutes per day switching between disconnected tools (Notion, sticky notes, text files, browser tabs) to track task progress. Existing solutions like Jira require account setup, team configuration, and internet connectivity — adding unnecessary overhead for individual workflows. Developers need a zero-setup, offline-capable task board that loads instantly and persists data locally.

### Goals
- **Goal 1:** Reduce daily task management overhead from 25-40 minutes to under 5 minutes by providing a single, unified board view
- **Goal 2:** Achieve zero-setup experience — developer can start using the board within 10 seconds of opening the app
- **Goal 3:** Enable offline-first workflow with 100% data persistence across browser sessions via localStorage

---

## 2. User Personas

### Persona 1: Alex, the Solo Freelancer
- **Role:** Freelance full-stack developer managing 2-3 client projects simultaneously
- **Background:** 3 years of experience, works remotely, uses VS Code daily. Currently tracks tasks in a mix of Notion, Apple Notes, and sticky notes on the monitor
- **Pain Points:**
  - Loses track of task status when switching between projects throughout the day
  - Spends 10-15 minutes each morning reconstructing what was "in progress" yesterday
  - Jira feels like overkill for solo work — too many clicks, too much configuration
- **Needs:** A single-page board that shows all tasks at a glance, works offline, and doesn't require sign-up
- **Tech Comfort:** High

### Persona 2: Sam, the Side-Project Builder
- **Role:** Full-time developer who works on 1-2 personal/open-source projects after hours
- **Background:** Uses Jira at work but refuses to use it for personal projects. Currently uses a plain text TODO.md file in each repo
- **Pain Points:**
  - TODO.md files get buried and forgotten — no visual priority indication
  - Can't see tasks across multiple repos in one view
  - Wants keyboard-driven workflow to match coding habits
- **Needs:** A fast, keyboard-friendly board that feels like a developer tool, not a management app
- **Tech Comfort:** High

---

## 3. Use Cases

### UC-1: Quick Task Capture
- **Actor:** Alex (Solo Freelancer)
- **Precondition:** Board is open in browser with at least one existing task visible
- **Flow:**
  1. Alex presses the `n` key on the keyboard
  2. A new task form/modal appears with cursor in the title field
  3. Alex types "Fix login API timeout issue" as the title
  4. Alex optionally adds a description: "Increase timeout from 5s to 15s in auth service"
  5. Alex presses Enter or clicks "Create"
  6. New task appears in the "To Do" column instantly
- **Expected Outcome:** Task is created and visible in under 10 seconds, data is persisted in localStorage

### UC-2: Visual Workflow Tracking
- **Actor:** Sam (Side-Project Builder)
- **Precondition:** Board has tasks in multiple columns
- **Flow:**
  1. Sam opens the task board after a day away
  2. Sam sees 3 columns: To Do (4 tasks), In Progress (2 tasks), Done (6 tasks)
  3. Sam drags "Write unit tests for auth module" from "To Do" to "In Progress"
  4. The card smoothly animates to the new column
  5. Column task counts update automatically
- **Expected Outcome:** Task status is updated visually and persisted. Sam knows exactly what to work on within 5 seconds of opening the board

### UC-3: Task Cleanup and Editing
- **Actor:** Alex (Solo Freelancer)
- **Precondition:** Board has completed tasks in the "Done" column
- **Flow:**
  1. Alex clicks on a task card "Deploy v2.1 to staging"
  2. Task detail view opens showing title, description, and status
  3. Alex edits the title to "Deploy v2.1 to staging ✅ — merged"
  4. Alex closes the detail view
  5. Alex right-clicks another task and selects "Delete"
  6. Confirmation prompt appears; Alex confirms
  7. Task is removed from the board
- **Expected Outcome:** Task is updated/deleted, changes persist in localStorage immediately

---

## 4. Functional Requirements

| ID | Requirement | Priority | Notes |
|----|-------------|----------|-------|
| FR-1 | The system shall display a Kanban board with three columns: "To Do", "In Progress", and "Done" | Must Have | Default columns, always visible |
| FR-2 | The system shall allow users to create a new task with a title (required) and description (optional) | Must Have | Task appears in "To Do" by default |
| FR-3 | The system shall allow users to edit an existing task's title and description | Must Have | Inline or modal editing |
| FR-4 | The system shall allow users to delete a task with a confirmation prompt | Must Have | Prevent accidental deletion |
| FR-5 | The system shall support drag-and-drop to move tasks between columns | Must Have | Smooth animation, visual feedback |
| FR-6 | The system shall persist all task data in browser localStorage | Must Have | Data survives page refresh and browser restart |
| FR-7 | The system shall support the `n` keyboard shortcut to open the new task form | Should Have | Focus should move to title field |
| FR-8 | The system shall display task count per column | Should Have | e.g., "To Do (4)" |
| FR-9 | The system shall load all persisted tasks on app startup within 500ms | Should Have | No loading spinners for < 50 tasks |
| FR-10 | The system shall allow users to reorder tasks within the same column via drag-and-drop | Could Have | Vertical reordering |

---

## 5. Non-Functional Requirements

### Performance
- Initial page load under 2 seconds on a standard broadband connection
- UI interactions (drag, click, type) respond within 100ms
- Board renders up to 50 tasks without noticeable performance degradation
- localStorage read/write operations complete within 50ms

### Security
- No user authentication required (single-user, local app)
- All data stored locally — no data transmitted over the network
- Input sanitization for task title and description to prevent XSS in rendered content

### Accessibility
- All interactive elements accessible via keyboard (Tab, Enter, Escape)
- Minimum color contrast ratio of 4.5:1 (WCAG 2.1 AA)
- Screen reader support for column names and task counts
- Focus management: modal traps focus, returns focus on close

### Browser Compatibility
- Chrome 90+, Firefox 88+, Safari 14+, Edge 90+ (latest 2 major versions)
- Responsive layout: usable on screens 768px and wider

### Data Persistence
- Data persists across page refreshes and browser restarts
- localStorage key: `taskboard-tasks` (JSON format)
- Graceful handling when localStorage is full (show user-friendly error)

---

## 6. Success Metrics

| Metric | Target | How to Measure | Timeline |
|--------|--------|----------------|----------|
| Task creation time | < 10 seconds from shortcut to saved task | User testing with 5 developers | At launch |
| Board load time | < 2 seconds with 20+ tasks | Lighthouse performance audit | At launch |
| Drag-and-drop success rate | 95%+ of drag operations complete without error | Manual QA testing across 3 browsers | At launch |
| Data persistence reliability | 100% data retained after 50 consecutive page refreshes | Automated test script | At launch |
| Daily active usage | 70% of testers return to use the board within 7 days | Self-reported usage log | 2 weeks post-launch |
| Task management time reduction | 60%+ reduction (from 25-40 min to < 10 min) | User survey comparing before/after | 30 days post-launch |

---

## 7. Scope

### In Scope (v1.0)
- Kanban board with 3 fixed columns (To Do, In Progress, Done)
- Task CRUD: Create, Read, Update, Delete
- Drag-and-drop between columns
- Keyboard shortcut: `n` key to create new task
- localStorage persistence (JSON format)
- Responsive layout (desktop-first, minimum 768px width)
- Clean, modern UI with smooth animations

### Out of Scope (future versions)
- **User authentication / multi-user** — This is a single-user, local tool (v2 consideration)
- **Backend / API / database** — All data stays in browser localStorage
- **Custom columns** — v1 ships with fixed 3 columns; customization deferred to v2
- **Task labels / tags / filters** — Keeps v1 simple; potential v2 feature
- **Due dates / reminders** — No notification system in v1
- **Mobile-optimized layout** — Desktop-first; mobile support deferred to v2
- **Data export / import** — No backup mechanism in v1
- **Real-time collaboration** — Explicitly out of scope; this is a solo tool

### Assumptions
- Users have modern browsers with JavaScript enabled and localStorage available
- Users have screens 768px or wider (desktop/laptop)
- Task volume will be under 100 tasks per user (localStorage limit ~5MB is sufficient)
- No internet connection required — app works fully offline after initial load

### Constraints
- No backend infrastructure — all logic runs client-side
- No npm packages for state management (use React built-in useState/useContext)
- Must be buildable with Vite and deployable as static files
- Total bundle size should stay under 500KB gzipped

---

## Appendix

### References
- Project Brief: `project-brief.md`
- Tech Stack: React 18 + Vite, TypeScript (strict), Vanilla CSS
- Conventions: See `agents.md` for full project conventions

### Revision History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2026-05-05 | Melik Tilla | Initial PRD generated from project brief |
