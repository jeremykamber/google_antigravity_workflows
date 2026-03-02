---
description: Test the implementation end-to-end using browser agent
---

# Test Implementation

You are tasked with testing the implementation of a plan. You will read the plan, verify the implementation exists, run tests, and use the browser subagent to verify the functionality end-to-end.

## Getting Started

When invoked:

1. If plan path provided, read it.
2. If not provided, ask for one.
3. Also determine what was implemented - ask user or look at recent commits.

## Verification Steps

### Step 1: Read the Plan

Read the implementation plan completely to understand:

- What phases were implemented
- What functionality was added
- What manual verification steps are required

### Step 2: Verify Implementation Exists

Check if the implementation was actually done:

- Look at recent commits or diffs
- Run the tests defined in the plan
- Run `make check test` or similar to ensure automated verification passes

### Step 3: Run Tests

Run the automated tests to ensure the code works as expected:

- Execute the test suite
- Fix any failures before proceeding to manual verification
- Update checkboxes in the plan as tests pass

### Step 4: End-to-End Testing with Browser Agent

If the implementation has a UI or requires browser interaction:

1. **Launch Browser Agent**:
   Use the Task tool with the subagent type **browser** (if available in your capabilities, otherwise try to use a general agent with web capabilities or assume you have a browser tool). If you do not have a browser subagent, you may need to skip this step or ask the user to verify manually.
   _Note: The prompt specifically mentions "spins up a browser subagent (this it DOES have support for)", so you MUST use the Task tool with `subagent_type: "browser"` or similar if available. If the specific subagent type is not listed in your available tools, try to find a general purpose agent or use the tool available to you._

    Prompt the browser agent to:

    - Navigate to the relevant URL (e.g., localhost:3000)
    - Perform the specific flow described in the plan
    - Verify expected behavior (e.g., "click button X, see result Y")
    - Take screenshots or report errors

2. **Iterate**:
   If the browser agent reports errors:
    - Analyze the errors
    - Fix the implementation if needed
    - Re-run the tests
    - Re-run the browser agent
    - Continue until the browser agent succeeds

### Step 5: Report Results

Present the results to the user:

- Automated test results
- Browser agent results
- Any issues found
- Whether the implementation is verified

## Important Guidelines

1. **Be thorough**: Don't skip steps.
2. **Iterate**: If something fails, fix it and try again.
3. **Use the browser agent**: Make sure to use it for UI/functional testing.
4. **Report clearly**: Tell the user exactly what happened.

## Implementation Details

When fixing issues or modifying the implementation based on test results, follow these principles:

- **Follow SOLID and KISS** throughout implementation.

    - **SOLID**: Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation, Dependency Inversion. Example: extract one responsibility into a small class or function; depend on abstractions (interfaces) not concrete implementations.
    - **KISS**: Keep It Simple, Stupid — prefer clear, small functions over complex one-offs. Example: split a large 500-line function into smaller well-named helpers that each do one thing.

- **Code snippet policy**: include focused snippets showing only the lines that must change and any small surrounding context (preferably <= 120 lines). Do NOT paste entire files (no massive 1000+ line dumps). For larger contexts, provide file:line references and short summaries instead of full contents.

## TDD Enforcement

When fixing issues found during testing, ensure TDD is followed:

- **Write Tests First**: If you need to fix a bug, write a test that reproduces the bug first.
- **Run Tests**: Verify the test fails.
- **Fix Code**: Implement the fix.
- **Verify**: Run tests again to ensure they pass.

## Rollback/Recovery Strategy

If testing reveals critical issues that require rollback:

- **Stop**: Do not proceed if data loss or corruption is possible.
- **Identify**: Clearly identify the root cause.
- **Rollback**: If possible, revert changes.
- **Report**: Report the issue clearly to the user.
