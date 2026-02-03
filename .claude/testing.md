# Testing: Test-First Development
We practice strict test-first development using the red-green-refactor cycle. Tests aren't just verification—they're design tools that reveal how the code wants to be shaped.

---

## REQUIRED: Use the test-first-partner Agent

**When writing new features or fixing bugs, delegate to the `test-first-partner` agent.**

Why? Humans (and AIs) naturally want to jump ahead. The agent enforces discipline—one test, one pass, one refactor, then stop. This prevents the "I'll just write a few more tests" trap that leads to untested assumptions.

```
Use: Task tool with subagent_type="test-first-partner"
```

---
## The Red-Green-Refactor Cycle

**One Test at a Time**
We write exactly one test, make it pass, and then refactor. Then move to the next test. This disciplined rhythm creates quality code through small, verified steps.

**🔴 RED - Write a Failing Test**
- Write ONE test for the next small piece of behavior
- Run it and watch it fail (proving the test works)
- The failure message should be clear and specific
- Don't write the next test yet

**🟢 GREEN - Make It Pass**
- Write the simplest code that makes THIS test pass
- Don't worry about perfection—just get to green
- It's okay if the implementation is naive or even hardcoded
- Don't anticipate future tests—solve only the current one

**🔵 REFACTOR - Improve the Design**
- Now that tests pass, improve the code
- Listen to what the code is telling you
- Remove duplication, clarify names, extract concepts
- Run tests after each small refactoring

**Repeat** - Write the next test. One test at a time reveals the design incrementally.

**Resist the Urge To:**
- Write multiple tests at once
- Design the whole solution upfront
- Anticipate future requirements in your implementation
- Skip the refactor step when tests pass

---

## Test Organization

- One test file per module being tested
- Group related tests with `describe` blocks
- Keep tests independent - no shared state between tests

## What to Test

**Do Test:**
- Behavior, not implementation
- Business rules in the domain model
- Public interfaces and contracts
- Edge cases and boundary conditions

**Don't Test:**
- Private methods (test through public interface)
- Private implementation details (test through public interface)
- Framework or library code (trust it works)
- Trivial pass-through code
- Simple getters/setters with no logic
- Types that have only getters/setters and no logic

## Writing Good Tests
**One Behavior Per Test**
- Each test should verify one specific thing
- Clear pass/fail: either it works or it doesn't
- Name tests to describe the behavior: `"empty cart has zero total"`

**Arrange-Act-Assert Pattern**
```typescript
// Arrange - Setup test data and conditions
const cart = new ShoppingCart();

// Act - Execute the behavior being tested
const total = cart.calculateTotal();

// Assert - Verify the expected outcome
expect(total).toBe(0);
```

**Keep Tests Simple**
- Tests should be easier to understand than the code they test
- Avoid complex logic in tests
- Make test failures obvious and debuggable

---


## Framework

- Use **Jest** with **ts-jest** for TypeScript support
- Test files: `tests/**/*.test.ts` or colocated as `*.test.ts`
- Run tests: `npx jest`
- Run in watch mode: `npx jest --watch`

## Test Structure

```typescript
describe("ClassName", () => {
    let instance: ClassName;

    beforeEach(() => {
        // Setup test fixtures
        instance = new ClassName();
    });

    afterEach(() => {
        // Cleanup after tests
    });

    it("should do something when condition", () => {
        // Arrange
        // Act
        // Assert
    });
});
```

## Naming Conventions

- Test files: `<module_name>.test.ts`
- Describe blocks: `describe("<ClassName>")` or `describe("<functionName>")`
- Test cases: `it("should <behavior> when <scenario>")`

## Assertions

Use Jest's built-in `expect` assertions:

| Assertion | Use Case |
|-----------|----------|
| `expect(a).toBe(b)` | Strict equality (===) |
| `expect(a).toEqual(b)` | Deep equality |
| `expect(x).toBeTruthy()` | Check truthy |
| `expect(x).toBeFalsy()` | Check falsy |
| `expect(x).toBeNull()` | Check null |
| `expect(x).toBeDefined()` | Check not undefined |
| `expect(fn).toThrow(Error)` | Check exception thrown |
| `expect(a).toContain(b)` | Check membership |
| `expect(a).toHaveLength(n)` | Check array/string length |

## Mocking

- Use Jest's built-in `jest.fn()` and `jest.mock()` for mocking dependencies
- Mock external services (APIs, databases) in unit tests
- Use `jest.spyOn` for spying on methods

```typescript
jest.mock("./external-api", () => ({
    ExternalAPI: jest.fn().mockReturnValue({
        fetch: jest.fn().mockResolvedValue({ data: "value" }),
    }),
}));

describe("Service", () => {
    it("calls external api", async () => {
        // Test code here
    });
});
```