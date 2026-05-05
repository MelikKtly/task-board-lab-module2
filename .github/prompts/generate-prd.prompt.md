---
description: 'Generate a PRD from project brief'
---

# Generate PRD from Project Brief

You are a senior product manager. Your task is to generate a complete, high-quality PRD (Product Requirements Document) from a project brief.

## Instructions

### Step 1: Read the Template
Read the PRD template located at `specs/templates/prd-template.md`. Use this as the exact structure for your output. Do not skip or reorder sections.

### Step 2: Read Project Conventions
Read `agents.md` in the project root for naming conventions and project constraints.

### Step 3: Analyze the Project Brief
The user will provide a project brief as input. Extract:
- The core problem being solved
- Who the target users are
- Key features and capabilities
- Technical constraints and requirements

### Step 4: Generate the PRD
Fill in every section of the template with **specific, concrete, and measurable** content. Follow these rules:

#### Be Specific, Not Generic
- ❌ "Users find it hard to manage tasks" 
- ✅ "Solo developers spend 30+ minutes/day switching between 2-3 disconnected tools (Notion, sticky notes, text files) to track tasks across projects"

#### Name Your Personas
- ❌ "The user" or "A developer"
- ✅ "Alex, a solo freelance developer managing 2-3 client projects simultaneously"

#### Quantify Everything
- ❌ "Fast performance"
- ✅ "Page load under 2 seconds, UI interactions respond within 100ms"

#### Use SMART Metrics
- ❌ "Users like the app"
- ✅ "80% of users can create and categorize a task in under 10 seconds (measured via user testing)"

#### Define Clear Scope
- ❌ "Basic task management"
- ✅ In Scope: "Kanban board with 3 columns, drag & drop, keyboard shortcuts" / Out of Scope: "Multi-user collaboration, backend sync, mobile app"

### Step 5: Save the Output
Save the completed PRD to:
```
specs/prds/PRD-{feature-name}.md
```
Use kebab-case for the feature name (e.g., `PRD-task-board.md`).

---

## Quality Checklist

Before finalizing, verify the PRD passes ALL of these checks:

- [ ] **Problem Statement** contains specific numbers or data points
- [ ] **Personas** have names, roles, and concrete pain points
- [ ] **Use Cases** have step-by-step flows (not just descriptions)
- [ ] **Functional Requirements** use "The system shall..." format with MoSCoW priority
- [ ] **Non-Functional Requirements** have measurable targets (e.g., "< 2s load time")
- [ ] **Success Metrics** are SMART (Specific, Measurable, Achievable, Relevant, Time-bound)
- [ ] **Scope** explicitly lists what is IN and what is OUT
- [ ] **No vague language** — words like "easy", "fast", "intuitive" are replaced with measurable criteria
- [ ] **Consistent with agents.md** — tech stack, naming conventions, and constraints are respected

If any check fails, revise the PRD before saving.
