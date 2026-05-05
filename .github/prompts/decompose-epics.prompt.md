---
description: 'Decompose PRD into Epics'
---

# Decompose PRD into Epics

You are a senior product manager. Your task is to break down an existing PRD into 3-4 high-level Epics that collectively deliver the full product vision.

## Instructions

### Step 1: Read the Inputs
1. Read the Epic template at `specs/templates/epic-template.md` — use this exact structure for each Epic.
2. Read `agents.md` for project conventions and naming rules.
3. Read the PRD provided by the user (from `specs/prds/`).

### Step 2: Analyze the PRD
Extract the following from the PRD:
- **Personas** — Who are the users?
- **Functional Requirements** — What must the system do?
- **Success Metrics** — How is success measured?
- **Scope** — What's in and out for v1?

### Step 3: Identify 3-4 Epics
Group the PRD's requirements into 3-4 Epics. Each Epic must pass ALL of these criteria:

#### Epic Quality Criteria

| # | Criteria | Question to Ask |
|---|----------|-----------------|
| 1 | **End-to-end value** | Does this Epic deliver something a user can actually use? |
| 2 | **Independently deployable** | Can this be shipped without waiting for other Epics? |
| 3 | **Maps to a Success Metric** | Which PRD metric does this Epic directly impact? |
| 4 | **Clear boundaries** | Can you clearly say what's IN and what's OUT of this Epic? |
| 5 | **Right size** | Is it big enough to be meaningful but small enough to estimate (3-8 stories)? |

#### Common Epic Patterns for Frontend Apps
- **Epic 1:** Core data model & CRUD operations (create, read, update, delete)
- **Epic 2:** UI layout & navigation (board view, columns, visual structure)
- **Epic 3:** Advanced interactions (drag & drop, keyboard shortcuts, filtering)
- **Epic 4:** Data persistence & polish (localStorage, error handling, responsive design)

> **Note:** These are suggestions, not requirements. Your Epics should reflect the specific PRD content.

### Step 4: Generate Each Epic
For each Epic, fill in the `epic-template.md` with:

- **Epic Title** — Clear, action-oriented name (e.g., "Task CRUD Operations", not "Tasks")
- **Description** — 2-3 sentences explaining the value delivered
- **Primary Persona** — Map to a specific named persona from the PRD
- **Success Criteria** — At least 2-3 measurable outcomes tied to PRD metrics
- **Scope/Complexity** — S/M/L with estimated story count
- **Dependencies** — List what must exist before this Epic can start
- **User Stories** — Leave as placeholder (will be filled by `/decompose-stories`)

### Step 5: Validate Epic Set
Before saving, verify the complete Epic set:

- [ ] **Full coverage** — All PRD functional requirements are covered by at least one Epic
- [ ] **No overlap** — Each requirement belongs to exactly one Epic
- [ ] **No gaps** — Nothing from the PRD's "In Scope" list is missing
- [ ] **Logical order** — Dependencies flow in one direction (Epic 1 → 2 → 3, not circular)
- [ ] **Persona coverage** — Every persona from the PRD benefits from at least one Epic
- [ ] **Metric coverage** — Every PRD success metric is addressed by at least one Epic

### Step 6: Save the Output
Save each Epic as a separate file:
```
specs/epics/EPIC-01-{name}.md
specs/epics/EPIC-02-{name}.md
specs/epics/EPIC-03-{name}.md
specs/epics/EPIC-04-{name}.md  (if needed)
```

Use kebab-case, zero-padded numbers (01, 02, 03).
Example: `EPIC-01-task-management.md`, `EPIC-02-board-layout.md`

---

## Anti-Patterns to Avoid

- ❌ **Technical Epics** — "Set up project" or "Create database" are not Epics (no user value)
- ❌ **Too granular** — If an Epic has only 1-2 stories, merge it with another
- ❌ **Too broad** — If an Epic has 10+ stories, split it
- ❌ **Overlapping scope** — Two Epics that both "handle tasks" need clearer boundaries
- ❌ **Missing persona** — Every Epic should clearly benefit a specific user
