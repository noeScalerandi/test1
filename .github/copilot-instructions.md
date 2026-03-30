# Copilot Instructions

## Purpose

This repository contains a Proof of Concept built around an agent-based workflow.  
The goal of any LLM or coding agent working in this codebase is to:

1. Understand the current architecture before making changes.
2. Preserve the separation of responsibilities between orchestration, agents, and configuration.
3. Prefer small, safe, traceable changes.
4. Read and honor project documentation before generating or modifying code.

---

## Project Architecture

The current application structure is:

```text
/
├── .github/
│   ├── workflows/injector.yml     <-- PoC execution engine
│   ├── copilot-instructions.md    <-- This file
│   ├── templates/                 <-- Document templates
│   │   ├── BUG_TEMPLATE.md
│   │   ├── FEATURE_TEMPLATE.md
│   │   ├── INCIDENT_TEMPLATE.md
│   │   └── SPEC_TEMPLATE.md
│   └── subagents/                 <-- Subagent definitions
│       ├── architect.md
│       ├── developer.md
│       ├── product-owner.md
│       └── qa.md
├── agents/                        <-- Agent logic
│   ├── researcher.py
│   └── writer.py
├── briefs/                        <-- Generated briefs (output)
├── specs/                         <-- Generated specs (output)
├── config/
│   └── settings.json
└── requirements.txt
```

---

## SDD Workflow Commands

When users invoke these commands, follow the instructions precisely:

### `Create brief for [feature-name]`

**Trigger:** User says "Create brief for X" or "Brief for X"

**Steps:**
1. Read the template from `.github/templates/FEATURE_TEMPLATE.md`
2. Ask the user for the required information to fill each section
3. Generate a completed brief document
4. Save the file to `briefs/{feature-name}.md` (kebab-case filename)
5. Confirm creation with a link to the file

**Example:**
- Input: `Create brief for payment-processing`
- Output: `briefs/payment-processing.md`

---

### `Create spec for [feature-name]`

**Trigger:** User says "Create spec for X" or "Spec for X"

**Steps:**
1. Read the template from `.github/templates/SPEC_TEMPLATE.md`
2. Check if a brief exists in `briefs/{feature-name}.md` — if yes, use it as context
3. Ask the user for any additional required information
4. Generate a completed spec with a unique Spec ID (format: `SDD-{FEATURE}-{NUMBER}`)
5. Save the file to `specs/SDD-{FEATURE}-{NUMBER}.md`
6. Confirm creation with a link to the file

**Example:**
- Input: `Create spec for payment-processing`
- Context: reads `briefs/payment-processing.md`
- Output: `specs/SDD-PAY-001.md`

---

### `Code [feature-name]` or `Implement [feature-name]`

**Trigger:** User says "Code X", "Implement X", or "Develop X"

**Steps:**
1. Look for the spec in `specs/` matching the feature name
2. If no spec exists, look for a brief in `briefs/`
3. If neither exists, ask the user to create a brief or spec first
4. Read the spec/brief as context
5. Invoke the **developer subagent** (`.github/subagents/developer.md`) with the context
6. Generate code following the spec requirements
7. Propose file locations based on the project architecture

**Example:**
- Input: `Code payment-processing`
- Context: reads `specs/SDD-PAY-001.md`
- Action: follows `developer.md` instructions to generate code

---

### `Report bug for [component]`

**Trigger:** User says "Report bug", "Bug report", or "Create bug for X"

**Steps:**
1. Read the template from `.github/templates/BUG_TEMPLATE.md`
2. Ask the user for details to fill each section
3. Generate a completed bug report
4. Output the bug report in markdown format

---

### `Report incident for [system]`

**Trigger:** User says "Report incident", "Incident report", or "Create incident for X"

**Steps:**
1. Read the template from `.github/templates/INCIDENT_TEMPLATE.md`
2. Ask the user for details about the incident
3. Generate a completed incident report
4. Output the incident report in markdown format

---

## Subagents

Subagents are specialized AI assistants that handle specific types of tasks.

### Available Subagents

| Subagent | File | Purpose |
|----------|------|---------|
| **Architect** | `.github/subagents/architect.md` | System design, architecture decisions |
| **Developer** | `.github/subagents/developer.md` | Code implementation |
| **Product Owner** | `.github/subagents/product-owner.md` | Requirements, user stories |
| **QA** | `.github/subagents/qa.md` | Testing, quality assurance |

### How to Invoke a Subagent

**Trigger:** User says "Call [subagent] subagent to [task]"

**Steps:**
1. Read the corresponding file from `.github/subagents/{subagent}.md`
2. Execute the instructions defined in that file
3. Apply the subagent's persona and rules to complete the task

**Examples:**
- `Call architect subagent to design the payment system`
- `Call developer subagent to implement the auth module`
- `Call qa subagent to create tests for the API`
- `Call product-owner subagent to write user stories`

---

## Context Chain

When working on a feature, always check for existing context in this order:

1. **Specs** (`specs/`) — Most detailed, use as primary context
2. **Briefs** (`briefs/`) — High-level requirements
3. **Templates** (`.github/templates/`) — Structure for new documents

This ensures continuity and consistency across the development workflow.

---

## AI Agent Reference Guide

**Purpose:** This document serves as the primary entry point for AI agents. It provides a comprehensive overview of the project structure, development guidelines, and links to specialized documentation for different aspects of the system.