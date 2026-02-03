# Development Philosophy
 This document captures our core beliefs and values about software development. These principles guide our decisions and shape how we approach problems.

 ---

 ## Core Values
 **Clarity Above All**
 - Code is read far more often than it's written
 - Write for the next person (often your future self)
 - Clarity is an act of kindness to your collaborators
 - Simple solutions are usually better than clever ones

 **Quality is Incremental**
 - Perfect code doesn't exit, but better code does
 - Small improvements compound over time
 - You don't have to make the code better every time, strive to make it less bad
 
 **Understanding Before Building**
 - Don't start coding until you understand the problem
 - Ask questions when requirements are unclear
 - Explore the domain before jumping to solutions

 ---

 ## How We Build Software
 **Test-First, Always**
 - Every feature begins with a failing test
 - One test at time-focus, implement, refator
 - Tests reveal the design, don't fight them
 - Red-green-refactor is our rhythm (see [testing.md](testing.md))

 **Work in Small Steps**
 - Write one test, make it pass, refactor
 - Never refactor on red-get to green first
 - Small steps make problems easier to debug

**Separation of Concerns**
- Domain layer: pure business logic, no external dependencies
- Service layer: coordination, orchestration, and boundary protection
- Infrastructure layer: databasees, API, external systems
- Exceptions at service boundaries (validate input, catch domain exceptions)
- Clear boundaries make testing and changes easy

---

## What We Value
**Behavior over Implementation**
- What the code does matters more than how
- Test behavior, not implementation details
- Implementation can change, behavior should stay stable
- Focus on contracts and interfaces, not internals

**Discipline Over Improvisation**
- Red-green-refactor: no shortcuts
- One test at a time: resist the urge to skip ahead
- The rhythm produces quality

**Error Handling Philosophy**
- Domain objects raise exceptions for violated business rules
- Services catch and handle exceptions at boundaries
- Don't let exceptions leak across architectural layers
- Make error messages helpful for debugging