# Epic: [EPIC TITLE]

**Epic ID:** EPIC-[NUMBER]
**PRD Reference:** [LINK TO PARENT PRD]
**Status:** Draft | Ready | In Progress | Done
**Owner:** [OWNER NAME]
**Date:** [DATE]

---

## 1. Description

<!-- Summarize the Epic in 2-3 sentences. Focus on WHAT value it delivers and WHY it matters. -->
[Describe the high-level feature or capability this Epic delivers. Explain how it contributes to the overall product goals. Keep it concise — save details for User Stories.]

---

## 2. Primary Persona

<!-- Which persona (from the PRD) benefits most from this Epic? -->

- **Name:** [PERSONA NAME from PRD]
- **Role:** [ROLE]
- **Key Need Addressed:** [What specific pain point or need does this Epic solve for them?]

<!-- 
Tip: Each Epic should clearly map to at least one persona. 
If an Epic doesn't benefit a specific persona, question whether it's needed.
-->

---

## 3. Success Criteria

<!-- Define measurable outcomes. How do we know this Epic is "done" AND "successful"? -->

| # | Criteria | Metric | Target |
|---|----------|--------|--------|
| SC-1 | [e.g., Users can create tasks] | [e.g., Task creation success rate] | [e.g., 100% — no errors] |
| SC-2 | [e.g., Tasks persist across sessions] | [e.g., Data retention after refresh] | [e.g., Zero data loss] |
| SC-3 | [e.g., Intuitive drag & drop] | [e.g., Task moved in < X seconds] | [e.g., Under 3 seconds] |

<!-- 
"Done" = All Stories completed and acceptance criteria met.
"Successful" = Success metrics from PRD are positively impacted.
Common mistake: Confusing "done" with "successful." Shipping isn't success — impact is.
-->

---

## 4. Scope & Complexity

### Complexity Estimate
- **Size:** [ S | M | L ]
- **Estimated Duration:** [e.g., 1 week / 2 weeks / 1 sprint]
- **Estimated Story Count:** [e.g., 3-5 stories]

### What's Included
- [Capability or feature included in this Epic]
- [Capability or feature included in this Epic]
- [Capability or feature included in this Epic]

### What's NOT Included
- [Explicitly excluded feature and why]
- [Feature deferred to another Epic]

<!-- 
Size guide:
  S = 1-3 stories, < 1 week, low risk
  M = 3-5 stories, 1-2 weeks, moderate risk  
  L = 5-8 stories, 2+ weeks, high risk — consider splitting
-->

---

## 5. Dependencies

<!-- What must exist or be completed BEFORE this Epic can start or be delivered? -->

### Technical Dependencies
- [ ] [e.g., Project scaffolding and build setup must be complete]
- [ ] [e.g., Component library / design system must be available]

### Epic Dependencies
- [ ] [e.g., EPIC-1 must be completed before this Epic can start]
- [ ] [e.g., No dependencies — can start independently]

### External Dependencies
- [ ] [e.g., No external APIs required]
- [ ] [e.g., Design mockups must be approved]

<!-- 
Tip: Fewer dependencies = better. Epics should be as independent as possible.
If an Epic has 3+ dependencies, consider restructuring.
-->

---

## 6. User Stories

<!-- This section will be filled after Epic decomposition. List Stories once created. -->

| Story ID | Title | Status | Priority |
|----------|-------|--------|----------|
| STORY-[EPIC].[1] | [STORY TITLE] | To Do | [Must/Should/Could] |
| STORY-[EPIC].[2] | [STORY TITLE] | To Do | [Must/Should/Could] |
| STORY-[EPIC].[3] | [STORY TITLE] | To Do | [Must/Should/Could] |

<!-- 
Stories will be generated using the decompose-stories prompt.
Each Story should be completable in 1-3 days and pass INVEST principles.
-->

---

## Revision History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | [DATE] | [AUTHOR] | Initial draft |
