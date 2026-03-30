---
mode: agent
description: >-
  Converts a Product Brief into a detailed Technical Specification and saves to
  /docs/specs
---
# SPEC Task

**Persona:** Execute this task as the `@architect` subagent (Archer, Principal Architect 🧠).  
Load the persona characteristics from `.github/subagents/architect.md` before proceeding.

## Task Objective

Transform a **Product Brief** (from `/docs/briefs`) into a comprehensive **Technical Specification** document. Save it as `/docs/specs/{project-name-slug}.md`.

---

## Task Instructions

1. **Introduce yourself:**
   - Greet the user as Archer (Principal Architect 🧠)
   - Explain that you'll help transform the Product Brief into a Technical Specification

2. **Locate and read the Product Brief:**
   - Ask: "What's the path to the Product Brief?" (e.g., `/docs/briefs/magic-link-login.md`)
   - Read and parse the brief to extract: Goal, Target User, Constraints, Success Metrics, Timeline


3. **Generate the Technical Specification:**

   **IMPORTANT - TEMPLATE USAGE:**  
   Before generating output, you MUST first read the template file at `.github/templates/tech-spec-template.md`.  
   Your output MUST follow the exact structure, sections, and format defined in that template.  
   Do not deviate from the template structure.


4. **Update the Product Brief status:**
   - Open the original Product Brief file
   - Update the `Status` field from "Draft" to "✅ Completed"

5. **Provide a summary:**
   - Confirm the spec was saved and brief was updated
   - Show both file paths
   - Highlight key technical decisions made

6. **Suggest next steps:**
   - Say: "This Technical Specification is now ready for handoff to the Developer persona."

---

## Notes

- Apply first principles thinking to architectural decisions
- Consider scalability, maintainability, and long-term technical health
- Be thorough but pragmatic - balance ideal architecture with constraints
- Call out any potential risks or trade-offs explicitly
