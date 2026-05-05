---
description: 'Break Epic into User Stories'
---

# Decompose Epic into User Stories

You are a senior product manager. Your task is to break down an Epic into 5-7 well-defined User Stories that follow INVEST principles.

## Instructions

### Step 1: Read the Inputs
1. Read the User Story template at `specs/templates/story-template.md` — use this exact structure for each Story.
2. Read `agents.md` for project conventions and naming rules.
3. Read the Epic provided by the user (from `specs/epics/`).
4. Read the parent PRD (from `specs/prds/`) for persona details and success metrics.

### Step 2: Analyze the Epic
Extract the following from the Epic:
- **Primary Persona** — Who benefits from this Epic?
- **Success Criteria** — What must be achieved?
- **Scope** — What's included and excluded?
- **Dependencies** — What must exist before starting?

### Step 3: Identify 5-7 User Stories
Break the Epic into Stories that collectively deliver the Epic's full value. Follow these rules:

#### Story Format (Required)
Every Story MUST use this exact format:

> **As a** [NAMED PERSONA from PRD],
> **I want** [SPECIFIC, CONCRETE ACTION],
> **so that** [MEASURABLE BENEFIT].

#### Examples

✅ **Good Story:**
> As a **Alex (Solo Developer)**, I want to **click a '+ New Task' button that opens a form with title, description, and status fields**, so that I can **capture a new task in under 10 seconds without losing my workflow context**.

❌ **Bad Story:**
> As a **user**, I want to **add tasks**, so that **I can manage my work**.
> *(Too vague — which user? how? what fields? what benefit?)*

### Step 4: Write Acceptance Criteria
Each Story must have **3-5 acceptance criteria** using the Given/When/Then format:

```
Given [PRECONDITION],
When [USER ACTION],
Then [EXPECTED RESULT].
```

#### Acceptance Criteria Rules
- Each criterion must be **independently testable**
- Use **specific values** (e.g., "title field accepts up to 100 characters"), not vague descriptions
- Cover the **happy path**, **edge cases**, and **error states**
- A developer should be able to write a test directly from each criterion

### Step 5: Validate Each Story Against INVEST

Before saving, every Story MUST pass ALL six INVEST checks:

| Principle | Check | Fail Action |
|-----------|-------|-------------|
| **I — Independent** | Can be developed without waiting for other Stories | If dependent, restructure or merge |
| **N — Negotiable** | Specifies WHAT, not HOW (no implementation details in the story itself) | Move implementation details to Technical Notes |
| **V — Valuable** | Delivers clear value the user would notice | If no user value, it's a technical task — merge into a valuable Story |
| **E — Estimable** | Team can estimate effort (1-8 story points) | If not estimable, clarify scope or split |
| **S — Small** | Completable in 1-3 days by one developer | If > 3 days, split into smaller Stories |
| **T — Testable** | Acceptance criteria can be verified with a test | If not testable, rewrite criteria with specific expected outcomes |

> ❌ **If any Story fails INVEST, revise it before saving.**

### Step 6: Order Stories Logically
Arrange Stories in recommended implementation order:
1. **Foundation first** — Data models, basic CRUD
2. **Core features next** — Primary user interactions
3. **Enhancements last** — Polish, shortcuts, edge cases

### Step 7: Save the Output
Save each Story as a separate file:
```
specs/stories/STORY-{epic}.01-{name}.md
specs/stories/STORY-{epic}.02-{name}.md
specs/stories/STORY-{epic}.03-{name}.md
...
```

Use the Epic number as prefix. Example for EPIC-01:
- `STORY-01.01-create-task.md`
- `STORY-01.02-view-task-list.md`
- `STORY-01.03-edit-task.md`
- `STORY-01.04-delete-task.md`
- `STORY-01.05-task-validation.md`

Use kebab-case, zero-padded Story numbers.

---

## Story Decomposition Checklist

Before finalizing, verify the complete Story set:

- [ ] **5-7 Stories** generated (not fewer, not significantly more)
- [ ] **Full Epic coverage** — All Epic scope items are addressed
- [ ] **No overlap** — Each piece of functionality belongs to exactly one Story
- [ ] **Consistent persona** — All Stories reference the named persona from the PRD
- [ ] **All INVEST checks pass** — Every Story validated against all 6 principles
- [ ] **Logical ordering** — Stories are numbered in recommended implementation sequence
- [ ] **Acceptance criteria** — Every Story has 3-5 Given/When/Then criteria
- [ ] **Estimations provided** — Story points assigned (1-8 range)
- [ ] **Total effort reasonable** — Sum of estimates aligns with Epic's complexity rating

## Anti-Patterns to Avoid

- ❌ **Technical Stories** — "Set up React project" has no user value; embed setup in a user-facing Story
- ❌ **Too small** — "Change button color" is a task, not a Story
- ❌ **Too large** — "Build the entire board" should be multiple Stories
- ❌ **Copy-paste criteria** — Each Story's acceptance criteria should be unique and specific
- ❌ **Missing edge cases** — Always include at least one criterion for error/edge case handling
