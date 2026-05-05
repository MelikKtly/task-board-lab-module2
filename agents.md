# Project Conventions — Personal Task Board

> This file defines project conventions for AI assistants working on this codebase.
> Follow these rules strictly when generating code, specs, or documentation.

---

## 1. Tech Stack

| Layer | Technology | Notes |
|-------|-----------|-------|
| **Framework** | React 18 | Functional components + hooks only |
| **Build Tool** | Vite | Fast dev server, HMR enabled |
| **Language** | TypeScript | Strict mode, no `any` types |
| **Styling** | Vanilla CSS | No Tailwind, no CSS-in-JS |
| **Data Storage** | localStorage | No backend, no API calls |
| **State Management** | React useState/useContext | No Redux or external state libs |
| **Testing** | Vitest + React Testing Library | Optional for lab scope |

### Key Constraints
- **No backend** — All data persists in browser localStorage
- **No external APIs** — App works fully offline
- **No heavy dependencies** — Minimize npm packages

---

## 2. Specification Structure

All project specifications live under the `specs/` directory:

```
specs/
├── templates/          # Reusable templates (do not edit directly for output)
│   ├── prd-template.md
│   ├── epic-template.md
│   └── story-template.md
├── prds/               # Generated PRDs
├── epics/              # Generated Epics
└── stories/            # Generated User Stories
```

### Prompt Library

Reusable GitHub Copilot prompt files are stored in:

```
.github/
└── prompts/
    ├── generate-prd.prompt.md
    ├── decompose-epics.prompt.md
    └── decompose-stories.prompt.md
```

---

## 3. Naming Conventions

### Spec Files

| Type | Format | Example |
|------|--------|---------|
| **PRD** | `PRD-{feature-name}.md` | `PRD-task-board.md` |
| **Epic** | `EPIC-{number}-{name}.md` | `EPIC-01-task-management.md` |
| **Story** | `STORY-{epic}.{number}-{name}.md` | `STORY-01.01-create-task.md` |

- Use **kebab-case** for all filenames (lowercase, hyphens)
- Epic numbers are **zero-padded** two digits: `01`, `02`, `03`
- Story numbers follow `{epic-number}.{story-number}` format

### Source Code Files (when implemented)

| Type | Format | Example |
|------|--------|---------|
| **Components** | `PascalCase.tsx` | `TaskCard.tsx` |
| **Hooks** | `camelCase.ts` | `useTaskBoard.ts` |
| **Types** | `camelCase.types.ts` | `task.types.ts` |
| **Utils** | `camelCase.ts` | `localStorage.ts` |
| **Styles** | `PascalCase.css` | `TaskCard.css` |

---

## 4. File Organization

### Project Root

```
task-board-lab-module2/
├── agents.md                    # This file — project conventions
├── lab-guide-ai-as-copilot.md   # Lab instructions (read-only)
├── .github/
│   └── prompts/                 # GitHub Copilot prompt files
├── specs/
│   ├── templates/               # PRD, Epic, Story templates
│   ├── prds/                    # Generated PRDs
│   ├── epics/                   # Generated Epics
│   └── stories/                 # Generated Stories
└── src/                         # Source code (when implementation begins)
    ├── components/              # React components
    ├── hooks/                   # Custom hooks
    ├── types/                   # TypeScript type definitions
    ├── utils/                   # Utility functions
    ├── App.tsx                  # Root component
    ├── main.tsx                 # Entry point
    └── index.css                # Global styles
```

### Rules for AI Assistants

1. **Always use templates** — When generating PRDs, Epics, or Stories, follow the templates in `specs/templates/`
2. **Follow naming conventions** — Use the exact file naming patterns defined above
3. **No backend code** — All persistence is via `localStorage`
4. **TypeScript strict** — No `any` types, define interfaces for all data structures
5. **Functional React** — Use hooks, not class components
6. **Keep components small** — One component per file, max ~150 lines
7. **Comment decisions** — Explain *why*, not *what*