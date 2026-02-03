# Planning: Think Before You Build
We plan before we code. Whether designing a new feature, contemplating a refactor, updating business logic, or fixing a bug, we take time to understand the problem and evaluate approaches before writing any implementation.

---

## REQUIRED: Use the typescript-planner Agent

**When planning features, evaluating approaches, or reviewing type designs, delegate to the `typescript-planner` agent.**

Why? It's easy to jump straight into code. The agent enforces a planning discipline—analyze what exists, recommend an approach with tradeoffs, and get alignment before implementation begins. This prevents the "I'll just start coding and figure it out" trap that leads to rework.

```
Use: Task tool with subagent_type="typescript-planner"
```

---

## When to Plan

**New Features**
- Understand the domain concept before writing types or code
- Identify what data structures and behaviors are needed
- Consider how the feature fits into the existing architecture

**Refactors**
- Identify what's wrong with the current design
- Define the target structure before moving code around
- Plan the sequence of safe, incremental changes

**Business Logic Changes**
- Clarify the rules before encoding them
- Identify edge cases and boundary conditions upfront
- Determine what existing tests need to change

**Bug Fixes**
- Reproduce and understand the bug first
- Identify the root cause, not just the symptom
- Consider whether the fix reveals a design problem

---

## The Planning Process

1. **Understand** — Read the relevant code, gather context, clarify requirements
2. **Analyze** — Identify constraints, tradeoffs, and risks
3. **Propose** — Present options with reasoning: "Option A is simpler; Option B handles edge cases better. I recommend A because..."
4. **Align** — Get agreement on the approach before implementation begins
5. **Hand off** — Pass the plan to the test-first-partner agent for implementation

---

## What a Good Plan Includes

- **What** the change accomplishes (the goal, not the code)
- **Where** it fits in the existing structure (which modules, which types)
- **How** it will be approached (sequence of steps, key decisions)
- **Why** this approach over alternatives (tradeoffs considered)
- **What could go wrong** (risks, edge cases, assumptions)

---

## What a Plan Does NOT Include

- Fully written implementation code
- Every line or detail spelled out — leave room for TDD to reveal the design
- Premature optimization or over-engineering
- Decisions about things that can be deferred

---

## From Plan to Implementation

Once a plan is agreed upon, hand off to the test-first-partner agent. The plan provides direction; TDD provides the implementation path. Let the tests reveal the detailed design — the plan sets the course, not the exact route.