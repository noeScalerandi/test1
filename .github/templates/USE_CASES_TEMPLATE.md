# {Feature Name} — Use Cases

## Actors

| Actor | Description |
|-------|-------------|
| {e.g., "Planner"} | {Role description — e.g., "Team lead responsible for capacity planning and hour allocation"} |
| {e.g., "Manager"} | {Role description — e.g., "Reviews and approves published plans"} |
| {e.g., "System"} | {e.g., "Automated processes — HR sync, capacity calculations, snapshot generation"} |

---

## User Stories

### US-01 — {Story Title}

**As a** {actor/role}
**I want** {action or capability}
**So that** {business value or outcome}

### US-02 — {Story Title}

**As a** {actor/role}
**I want** {action or capability}
**So that** {business value or outcome}

### US-03 — {Story Title}

**As a** {actor/role}
**I want** {action or capability}
**So that** {business value or outcome}

---

## Use Case Scenarios

### UC-01 — {Use Case Title} (US-01)

**Preconditions:** {What must be true before the use case starts — e.g., "Planner is authenticated and has an active team assigned"}

#### Main Scenario

1. {Actor action — e.g., "The Planner accesses the Planning section and selects a period (weekly, biweekly, or monthly)"}
2. {System response — e.g., "The system displays a planning grid with rows per resource and columns per week"}
3. {System preloads — e.g., "The system preloads approved leaves and holidays from HR, reducing available capacity automatically"}
4. {Core interaction — e.g., "The Planner assigns hours per resource, project, and concept, distinguishing:"}
   - a) {Category — e.g., "Billable: hours or capacity percentage"}
   - b) {Category — e.g., "Non-billable: fixed hours by type (Bench, Training, Events)"}
5. {Validation — e.g., "The system validates in real time that total allocation does not exceed available capacity"}
6. {Completion — e.g., "The Planner saves as Draft or Publishes the plan"}

#### Alternative Scenarios

**1a. {Condition — e.g., "Allocation below 100%"}**
{Behavior — e.g., "The system shows a visual alert. In Draft mode, partial allocation is allowed. To Publish, 100% allocation is required."}

**4a. {Condition — e.g., "Resource availability conflict"}**
{Behavior — e.g., "If the resource is shared with another project and total allocation exceeds capacity, the system shows a conflict alert with details of the overlapping project."}

#### Error Scenarios

**3e. {Condition — e.g., "HR system unavailable"}**
{Behavior — e.g., "The system displays last cached leave data with a warning that availability may not reflect recent changes. The Planner can proceed but cannot Publish until HR data is refreshed."}

**Postconditions:** {What is true after the use case completes — e.g., "Plan is saved as Draft or Published with an immutable snapshot"}

---

### UC-02 — {Use Case Title} (US-02, US-03)

**Preconditions:** {What must be true}

#### Main Scenario

1. {Step}
2. {Step}
3. {Step}

#### Alternative Scenarios

**{N}a. {Condition}**
{Behavior}

#### Error Scenarios

**{N}e. {Condition}**
{Behavior}

**Postconditions:** {What is true after completion}

---

## UX/UI References

{Link to Figma, wireframes, or screenshots that illustrate the use case scenarios above. See also the UX/UI section in [spec.md](./spec.md#uxui) for the full design reference list.}
