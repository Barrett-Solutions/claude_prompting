# Code Style Guide

This guide defines coding standards and conventions for our project. Consistency makes code easier to read, maintain, and collaborate on.

---

## General Principles

**Clarity Over Cleverness**
- Write code that is easy to understand, not code to show off
- If it needs extensive comments to explain, it probably needs refactoring
- Choose obvious solutions over clever ones

**Naming Matters**
- Use descriptive names that reveal intent
- Functions and methods should be verbs: `calculateTotal()`, `validateInput()`
- Classes and types should be nouns: `UserAccount`, `OrderProcessor`
- Booleans should read like questions: `isValid`, `hasPermission`, `canEdit`

**Keep It Small**
- Functions should do one thing well
- Classes should have a single, clear responsibility
- Files should be cohesive and focused

---

## Project Structure

This project uses a **src/ layout**:

```
src/
test/             # All tests in separate directory
```

---

## Formatting
**Indentation**
- Use consistent indentation: *tabs*
- Be consistent across entire project

**Line Length**
- Aim for 80-120 characters per line
- Break long lines at logical points
- Don't sacrifice readability for line length rules

**Whitespace**
- Use blank lines to separate logical sections
- Add space around operators: `x = a + b` not `x=a+b`
- One statement per line

**When to comment**
- Explain *why* not *what*
- Document non-obvious decisions
- Warn about gotchas or edge cases
- Provide examples for complex APIs

**When NOT to Comment**
- Don't explain what the code obviously does
- Don't leave commented-out code
- Don't appoligize for code quality (fix it instead)

**Documentation**
- Public APIs and interfaces need clear documentation
- Include parameter descriptions and return values
- Provide usage examples for complex functionality

---