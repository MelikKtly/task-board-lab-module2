# Module 02 Lab Guide: Hands-On PRD Creation with AI (AI-as-Copilot Version)

**Module:** 02 - Spec Hierarchy: PRD Creation
**Duration:** 75 minutes
**Format:** Individual work with peer review
**Difficulty:** Intermediate
**Approach:** Use AI to create your prompts and templates (not copy/paste!)

---

## Lab Overview

**What You'll Build:**
Starting from a project brief, you'll use AI to help you create templates and prompts, then use those to generate a complete PRD, decompose it into Epics and User Stories, and build a reusable prompt library.

**Learning Objectives:**
By the end of this lab, you will be able to:
1. ✅ **Use AI to create** reusable prompt library for spec generation
2. ✅ **Use AI to design** templates for PRDs, Epics, and Stories
3. ✅ Generate PRDs iteratively using your AI-created prompts
4. ✅ Decompose PRDs into Epics representing complete user workflows
5. ✅ Write User Stories with acceptance criteria following INVEST principles
6. ✅ Apply the meta-pattern: **AI helps you build AI tools**

**Key Difference from Standard Lab:**
Instead of copying provided prompts and templates, you'll **ask AI to create them for you**. This teaches you to use AI as a copilot for building your AI workflows.

**Prerequisites:**
- Completion of Module 01 (Foundations - Precision Principle)
- Access to GitHub Copilot or Claude in VS Code
- Basic understanding of software development workflows

**Deliverables:**
- [ ] AI-generated templates (PRD, Epic, Story)
- [ ] AI-generated prompt library with 3-4 saved prompts
- [ ] PRD generated from project brief
- [ ] 3-4 Epic definitions with clear scope
- [ ] 5-7 User Stories with acceptance criteria
- [ ] Agents.MD configuration file

---

## About GitHub Copilot Prompt Files

**What are Prompt Files?**
GitHub Copilot supports **custom prompt files** that let you create reusable prompts for common tasks. These are markdown files with a special extension and optional configuration.

**File Naming Convention:**
- Files must end with `.prompt.md` (e.g., `generate-prd.prompt.md`)
- Use kebab-case for filenames (e.g., `decompose-epics.prompt.md`)
- Store in `.github/prompts/` folder in your workspace

**How to Use Prompt Files:**
- Type `/prompt-name` in GitHub Copilot Chat to invoke your prompt
- Example: `/generate-prd` runs the `generate-prd.prompt.md` file
- Copilot loads the prompt and applies it to your current context

**Optional: YAML Frontmatter**
You can add configuration at the top of your prompt file:

```markdown
---
description: 'Generate a PRD from a project brief'
mode: 'agent'
---

Your prompt content here...
```

**Official Documentation:**
- **GitHub Copilot Prompt Files Tutorial:** https://docs.github.com/en/copilot/tutorials/customization-library/prompt-files/your-first-prompt-file
- **VS Code Prompt Customization:** https://code.visualstudio.com/docs/copilot/customization/prompt-files
- **Community Examples:** https://github.com/github/awesome-copilot

> **Note:** Prompt files are currently in **public preview** and available in VS Code and JetBrains IDEs.

---

## Lab Structure & Timing

| **Phase** | **Activity** | **Duration** | **Checkpoint** |
|-----------|--------------|--------------|----------------|
| **Phase 1** | Setup & AI-Generated Templates | 25 min | ✅ Folders created, AI-generated templates saved |
| **Phase 2** | AI-Generated Prompt Library | 15 min | ✅ 3 prompts created by AI and saved |
| **Phase 3** | PRD Generation | 10 min | ✅ PRD generated using your tools |
| **Phase 4** | Epic & Story Decomposition | 15 min | ✅ 3-4 Epics, 5-7 Stories |
| **Phase 5** | Peer Review & Sharing | 10 min | ✅ Feedback received |

**Total:** 75 minutes

---

## Phase 1: Setup & AI-Generated Templates (25 minutes)

### **Step 1: Set Up Your Workspace (5 minutes)**

Create your project structure:

```bash
mkdir task-board-lab
cd task-board-lab

# Create spec folders
mkdir -p specs/templates

# Create prompt library folder for GitHub Copilot
mkdir -p .github/prompts

# Create output folders
mkdir -p specs/prds specs/epics specs/stories
```

---

### **Step 2: Use AI to Create Your Templates (15 minutes)**

**Instead of copying templates, ask AI to create them for you.**

#### **Template 1: PRD Template**

**Ask your AI assistant:**

```
I need a PRD (Product Requirements Document) template for software projects.
Create a markdown template that includes these sections:

1. Overview (Purpose, Problem Statement, Goals)
2. User Personas (Who are we building for?)
3. Use Cases (Key scenarios)
4. Functional Requirements (What the system must do)
5. Non-Functional Requirements (Performance, security, etc.)
6. Success Metrics (How we measure success)
7. Scope (What's in, what's out)

Format it as a template with placeholders like [DESCRIPTION HERE].
Save the output to specs/templates/prd-template.md
```

**Review the AI's output:**
- Does it have all 7 sections?
- Are there helpful placeholders?
- Are there guidance comments for each section?

**If needed, refine:**
```
Add more guidance for the "Success Metrics" section.
Include examples of SMART metrics in comments.
```

---

#### **Template 2: Epic Template**

**Ask your AI assistant:**

```
I need an Epic template for breaking down PRDs into large features.
Create a markdown template that includes:

1. Epic Title
2. Description (2-3 sentences)
3. Primary Persona (who benefits most)
4. Success Criteria (measurable outcomes)
5. Scope/Complexity (S/M/L estimate)
6. Dependencies (what must exist first)
7. User Stories placeholder (will be filled later)

Format with placeholders and helpful comments.
Save to specs/templates/epic-template.md
```

---

#### **Template 3: User Story Template**

**Ask your AI assistant:**

```
I need a User Story template following INVEST principles.
Create a markdown template that includes:

1. Story ID and Title
2. User Story format: "As a [persona], I want [action] so that [benefit]"
3. Acceptance Criteria (3-5 specific, testable conditions)
4. Technical Notes (optional implementation hints)
5. Estimation (story points or days)
6. INVEST validation checklist in comments

Format with placeholders and guidance.
Save to specs/templates/story-template.md
```

---

### **Step 3: Create Your agents.md with AI Help (5 minutes)**

**Ask your AI assistant:**

```
Create an agents.md file that establishes project conventions for this task board project.

Include:
1. Tech Stack: React 18 + Vite, TypeScript, localStorage (no backend)
2. Specification Structure: where PRDs/Epics/Stories are stored
3. Naming Conventions: how to name spec files
4. File organization

Make it clear and concise so AI assistants can follow these conventions.
Save to agents.md in project root.
```

**Review and refine if needed.**

**✅ Checkpoint:** You have:
- Folder structure created
- **3 AI-generated templates** in `specs/templates/`
- `agents.md` with conventions (also AI-generated)

---

## Phase 2: AI-Generated Prompt Library (15 minutes)

Instead of copying prompts, you'll **use AI to create prompts for you**.

### **Step 4: Create "Generate PRD" Prompt with AI (5 minutes)**

**Ask your AI assistant:**

```
I need a reusable GitHub Copilot prompt file for generating PRDs from project briefs.

Create a prompt file (.prompt.md format) that:
1. Includes YAML frontmatter with description: "Generate a PRD from project brief"
2. Instructs AI to read the PRD template from specs/templates/prd-template.md
3. Takes a project brief as input
4. Generates a complete PRD with specific, measurable details
5. Includes a quality checklist (problem has numbers, personas are named, metrics are SMART, scope is clear)
6. Saves output to specs/prds/PRD-{feature-name}.md

Format this as a GitHub Copilot prompt file that I can invoke with /generate-prd
Save to .github/prompts/generate-prd.prompt.md
```

**Expected format example:**
```markdown
---
description: 'Generate a PRD from project brief'
mode: 'agent'
---

Using the PRD template in specs/templates/prd-template.md, create a complete PRD.

[Rest of prompt instructions...]
```

**Review the generated prompt:**
- Is it clear and actionable?
- Does it have YAML frontmatter?
- Does it reference the template?
- Does it emphasize specificity over generic content?

**✅ You can now invoke this with:** `/generate-prd` in GitHub Copilot Chat

---

### **Step 5: Create "Decompose Epics" Prompt with AI (5 minutes)**

**Ask your AI assistant:**

```
Create a reusable GitHub Copilot prompt file for decomposing PRDs into Epics.

Create a .prompt.md file that:
1. Includes YAML frontmatter with description: "Decompose PRD into Epics"
2. Reads an existing PRD
3. Identifies 3-4 high-level Epics
4. Each Epic must: deliver end-to-end value, be independently deployable,
   map to a Success Metric from the PRD, have clear boundaries
5. Uses the epic-template.md format
6. Saves output to specs/epics/EPIC-{number}-{name}.md

Format for GitHub Copilot so I can invoke with /decompose-epics
Save to .github/prompts/decompose-epics.prompt.md
```

**✅ You can now invoke this with:** `/decompose-epics` in GitHub Copilot Chat

---

### **Step 6: Create "Decompose Stories" Prompt with AI (5 minutes)**

**Ask your AI assistant:**

```
Create a reusable GitHub Copilot prompt file for breaking Epics into User Stories.

Create a .prompt.md file that:
1. Includes YAML frontmatter with description: "Break Epic into User Stories"
2. Reads an Epic
3. Creates 5-7 User Stories
4. Each story must: follow "As a [persona] I want [action] so that [benefit]" format,
   be completable in 1-3 days, have 3-5 acceptance criteria, pass INVEST principles
5. Uses the story-template.md format
6. Saves to specs/stories/STORY-{epic}.{number}-{name}.md

Format for GitHub Copilot so I can invoke with /decompose-stories
Save to .github/prompts/decompose-stories.prompt.md
```

**✅ You can now invoke this with:** `/decompose-stories` in GitHub Copilot Chat

**✅ Checkpoint:** You have:
- 3 AI-generated prompts saved in `.github/prompts/` with `.prompt.md` extension
- All prompts can be invoked with `/prompt-name` in GitHub Copilot Chat
- All prompts reference your AI-generated templates
- Ready to use your custom-built AI toolkit!

---

## Phase 3: PRD Generation (10 minutes)

### **Step 7: Run Your AI-Created Prompt (7 minutes)**

Now use the prompt that AI created for you to generate a PRD.

**The Project Brief** (this is your only input):

> **Personal Task Board** - A React app (frontend only) with localStorage
>
> - **Problem:** Developers need a quick task board without heavy tools like Jira
> - **User:** Solo developer managing work across 2-3 projects
> - **Features:** Kanban board (To Do / In Progress / Done), drag & drop, keyboard shortcuts
> - **Tech:** React + Vite, no backend, data in localStorage
>
> See `project-brief.md` for full details.

**Run your saved prompt:**

1. Open GitHub Copilot Chat in VS Code
2. Type `/generate-prd` and press Enter
3. Provide the project brief above as context
4. Let AI generate the PRD following your custom prompt instructions

**Alternative method:**
- Open your `.github/prompts/generate-prd.prompt.md` file
- Click the play button in the editor to run the prompt
- Or use Command Palette: "Chat: Run Prompt"

**What happens:**
- AI reads your AI-generated template
- AI follows your AI-generated prompt instructions
- AI respects your `agents.md` conventions
- **All created by AI, orchestrated by you!**

---

### **Step 8: Quick Review (3 minutes)**

Check your generated PRD:

| Criteria | Present? | Action if Missing |
|----------|----------|-------------------|
| **Problem has numbers** | ✅/❌ | Ask AI to quantify |
| **Personas are named** | ✅/❌ | Ask AI to add names |
| **Metrics are SMART** | ✅/❌ | Ask AI to make measurable |
| **Scope is clear** | ✅/❌ | Ask AI to clarify boundaries |

**✅ Checkpoint:** PRD generated using your AI-created toolkit.

---

## Phase 4: Epic & Story Decomposition (15 minutes)

### **Step 9: Generate Epics (7 minutes)**

**Run your AI-created "decompose-epics" prompt:**

1. Open GitHub Copilot Chat in VS Code
2. Type `/decompose-epics` and press Enter
3. Provide your generated PRD as context
4. Let AI decompose into 3-4 Epics

**Quick validation:**
- Each Epic maps to a persona? ✅/❌
- Each Epic has success metric? ✅/❌
- Each Epic independently deployable? ✅/❌

---

### **Step 10: Generate Stories (8 minutes)**

**Run your AI-created "decompose-stories" prompt:**

1. Choose your most critical Epic
2. Open GitHub Copilot Chat in VS Code
3. Type `/decompose-stories` and press Enter
4. Provide the Epic as context
5. Let AI generate 5-7 User Stories

**INVEST quick check:**
- Independent? ✅/❌
- Small (1-3 days)? ✅/❌
- Testable criteria? ✅/❌

**✅ Checkpoint:** You have Epics and Stories generated using entirely AI-created tools.

---

## Phase 5: Peer Review & Sharing (10 minutes)

### **Step 11: Peer Review Exchange (8 minutes)**

**Find a partner.** Each person presents (4 minutes each):

1. **Your AI-Generated Templates** (1 minute):
   - Show one template AI created for you
   - How does it compare to what you would have written?

2. **Your AI-Generated Prompts** (1 minute):
   - Show one prompt AI created
   - Did AI include something you wouldn't have thought of?

3. **The Full Flow** (2 minutes):
   - Walk through: AI creates tools → You use tools → Generate specs
   - Show one refinement example

**Peer Feedback:**

✅ **Worked Well:** "Your AI-generated prompt includes..."

🔧 **Suggestion:** "You could ask AI to add [X] to your template..."

❓ **Question:** "How did you refine the AI-generated [template/prompt]?"

---

### **Step 12: Meta-Reflection (2 minutes)**

**Reflection questions:**

1. **How does using AI to create your tools differ from copying provided tools?**
2. **What did AI include in templates/prompts that surprised you?**
3. **When would you use AI to create tools vs. use standard templates?**

**Key insight:** You just used AI to build the tools that you then used with AI. This meta-pattern is powerful—AI helps you customize your AI workflows.

**✅ Checkpoint:** Shared your AI-generated toolkit and received feedback.

---

## Lab Completion Checklist

Before moving to the next module, ensure you have:

**AI-Generated Toolkit:**
- [ ] `specs/templates/prd-template.md` (created by AI)
- [ ] `specs/templates/epic-template.md` (created by AI)
- [ ] `specs/templates/story-template.md` (created by AI)
- [ ] `.github/prompts/generate-prd.prompt.md` (created by AI, invoke with `/generate-prd`)
- [ ] `.github/prompts/decompose-epics.prompt.md` (created by AI, invoke with `/decompose-epics`)
- [ ] `.github/prompts/decompose-stories.prompt.md` (created by AI, invoke with `/decompose-stories`)

**Generated Specs (using your AI-created toolkit):**
- [ ] `/specs/prds/` - PRD generated from project brief
- [ ] `/specs/epics/` - 3-4 Epics mapped to personas
- [ ] `/specs/stories/` - 5-7 Stories passing INVEST

**Configuration:**
- [ ] `agents.md` with project conventions (created by AI)

**Process Validation:**
- [ ] You used AI to create templates (not copied them)
- [ ] You used AI to create prompts (not copied them)
- [ ] You used your AI-created prompts to generate specs
- [ ] All specs follow your conventions
- [ ] You received peer feedback

**✅ If you checked all boxes above, you've successfully completed Module 02 (AI-as-Copilot version)!**

---

## Troubleshooting Guide

### **Common Issues & Solutions**

#### **Issue: AI-generated template is too generic**
**Symptoms:** Template has basic sections but lacks helpful guidance
**Solution:** Ask AI to enhance it

**Refinement prompt:**
```
This template needs more guidance. For each section, add:
- 2-3 bullet points explaining what should go there
- An example in comments showing good vs. bad content
- Common mistakes to avoid
```

---

#### **Issue: AI-generated prompt is too vague**
**Symptoms:** Prompt doesn't give AI clear enough instructions
**Solution:** Ask AI to make it more specific

**Refinement prompt:**
```
This prompt needs to be more specific. Add:
- Clear step-by-step instructions
- Quality criteria with examples
- Specific formatting requirements
- What to avoid (common mistakes)
```

---

#### **Issue: Not sure what to ask AI for**
**Symptoms:** Blank slate paralysis—don't know how to request templates/prompts
**Solution:** Use the examples in this lab guide as starting points

**Pattern for requesting templates:**
```
Create a [ARTIFACT TYPE] template that includes:
1. [Section 1]
2. [Section 2]
3. [Section 3]

Format with [SPECIFIC FORMATTING REQUESTS].
Include [GUIDANCE/EXAMPLES/COMMENTS].
Save to [FILE PATH].
```

**Pattern for requesting prompts:**
```
Create a reusable prompt for [TASK].

The prompt should:
1. [Input requirement 1]
2. [Processing step 1]
3. [Output requirement 1]
4. [Quality criteria]

Create this as a saved prompt file.
Save to [FILE PATH].
```

---

#### **Issue: AI-generated artifacts conflict with each other**
**Symptoms:** Prompt references template sections that don't exist
**Solution:** Create artifacts in order, provide context

**Better approach:**
1. Create templates first
2. Show AI the templates when creating prompts
3. Ask AI: "Based on the template I just created, now create a prompt that uses it"

**Example:**
```
I just created this PRD template: [paste template]

Now create a prompt that generates PRDs using this exact template structure.
The prompt should reference each section by name.
```

---

#### **Issue: Running out of time**
**Priority order:**

1. **Don't skip:** AI-generated templates (core deliverable)
2. **Don't skip:** At least 2 AI-generated prompts (generate-prd, decompose-epics)
3. **Can abbreviate:** Generate fewer stories (3-4 instead of 5-7)
4. **Can skip:** Third prompt (decompose-stories)—use AI directly instead
5. **Can skip:** Peer review (do async)

**The toolkit is the goal**—templates and prompts you created with AI are more valuable than the specs you generate with them.

---

## Post-Lab Resources

### **For Continued Learning:**

**Prompt Engineering for Tool Creation:**
- OpenAI Prompt Engineering Guide: https://platform.openai.com/docs/guides/prompt-engineering
- Anthropic Prompt Library: https://docs.anthropic.com/claude/prompt-library
- GitHub Copilot Best Practices: https://docs.github.com/en/copilot

**Meta-Learning (AI Creating AI Tools):**
- "Using AI to Build AI Workflows" (Maven course)
- GitHub Copilot Custom Instructions: https://docs.github.com/en/copilot/customizing-copilot
- Building Prompt Libraries (community practices)

**Template & Spec Standards:**
- GitHub Spec Kit: https://github.com/github/spec-kit
- Atlassian Templates: https://www.atlassian.com/software/confluence/templates
- SVPG Product Specs: https://www.svpg.com/assets/Files/goodprd.pdf

### **Practice Opportunities:**

**Extend Your AI Toolkit:**
- Ask AI to create more templates (Technical Design Doc, API Spec, Test Plan)
- Ask AI to create validation prompts (Check if PRD is complete)
- Ask AI to create refinement prompts (Improve acceptance criteria)

**Apply to Your Work:**
- Use AI to create templates specific to your company's needs
- Build a prompt library for your team's common tasks
- Share your AI-generated toolkit with colleagues

**Challenge Yourself:**
- Compare AI-generated template vs. standard template from GitHub Spec Kit
- Create two templates with different AI assistants—how do they differ?
- Ask AI to create a prompt that improves other prompts (meta-meta!)

---

## Key Differences: AI-as-Copilot vs. Standard Lab

### **Standard Lab Approach:**
```
[Instructor provides templates]
        ↓
[You copy templates]
        ↓
[You copy prompts]
        ↓
[You use prompts with templates]
        ↓
[You generate specs]
```

### **AI-as-Copilot Approach:**
```
[You ask AI to create templates]
        ↓
[You review & refine AI's templates]
        ↓
[You ask AI to create prompts using those templates]
        ↓
[You review & refine AI's prompts]
        ↓
[You use AI-created prompts with AI-created templates]
        ↓
[You generate specs]
```

### **Why AI-as-Copilot?**

**Advantages:**
- ✅ **Customization:** Templates/prompts match your exact needs
- ✅ **Learning:** You understand why each section exists (because you reviewed AI's reasoning)
- ✅ **Ownership:** Tools are yours, not copied
- ✅ **Flexibility:** Easy to modify for different project types
- ✅ **Meta-skill:** You learn to use AI to build AI tools

**Trade-offs:**
- ⏱️ Takes slightly more time upfront
- 🧠 Requires more active thinking
- 🎯 Need to validate AI's outputs (AI can make mistakes)

**When to use AI-as-Copilot approach:**
- When you need customized templates for your domain
- When standard templates don't fit your workflow
- When you want to deeply understand the structure
- When building reusable tools for your team

**When to use Standard approach:**
- When you need to move fast with proven templates
- When learning the standard structure for the first time
- When working with strict company standards
- When teaching novices who need clear examples

---

## Summary & Next Steps

**What You Accomplished:**

In this 75-minute lab, you:
✅ Used AI to create 3 spec templates (PRD, Epic, Story)
✅ Used AI to create 3 reusable prompts
✅ Generated PRD/Epics/Stories using your AI-created toolkit
✅ Applied the meta-pattern: **AI builds tools → You use tools**
✅ Built a customized, reusable toolkit (not copied generic templates)

**Key Takeaways:**

1. **AI as Tool Creator** - AI can build your workflows, not just execute tasks
2. **Review & Refine** - AI's first draft is rarely perfect; your judgment improves it
3. **Customization > Standardization** - AI-created tools match your exact needs
4. **Toolkit Compounds** - Each template/prompt you build adds to your library
5. **Meta-Learning** - Learning to create tools with AI is more valuable than using pre-made tools

**Comparison to Standard Approach:**
- You invested more time upfront creating tools
- You own tools customized to your needs
- You understand *why* each section/instruction exists
- You can easily modify tools for different project types

---

**End of Lab Guide (AI-as-Copilot Version)**
**Version:** 2.0-copilot
**Last Updated:** December 2024
**Module:** 02 - Spec Hierarchy: PRD Creation
**Approach:** AI-as-Copilot (AI creates the tools you use)
