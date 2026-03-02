---
description: Update existing implementation plans based on feedback with thorough research
---

# Plan Update Protocol (Single Agent)

You are tasked with updating existing implementation plans based on user feedback. You must be skeptical, thorough, and ensure all changes are grounded in the actual codebase reality through direct exploration.

## Process Steps

### Step 1: Read and Understand Current Plan

1. **Read the existing plan file COMPLETELY**:

- Use file reading tools **without** limit/offset parameters.
- Understand the current structure, phases, and scope.
- Note the success criteria and implementation approach.

2. **Understand the requested changes**:

- Parse exactly what the user wants to add, modify, or remove.
- Identify if these changes require fresh codebase validation.
- Determine the total scope of the update.

### Step 2: Direct Codebase Research

**Perform all necessary research yourself before proposing changes.** Do not delegate this to sub-tasks.

If the user's feedback requires understanding new code patterns or validating assumptions:

1. **Search the codebase**: Use `grep`, `find`, or list directory tools to locate relevant files and symbols.
2. **Analyze implementation details**: Read the identified files **fully** into your context to understand logic, dependencies, and existing patterns.
3. **Validate assumptions**: If the user suggests a change that seems technically risky, verify the feasibility by checking the actual code constraints.

### Step 3: Present Understanding and Approach

Before writing to the file, confirm your findings with the user:

```text
Based on your feedback, I understand you want to:
- [Change 1 with specific detail]
- [Change 2 with specific detail]

My research into the codebase found:
- [Relevant code pattern or constraint discovered during Step 2]
- [Important discovery that affects the change]

I plan to update the plan by:
1. [Specific modification to make]
2. [Another modification]

Does this align with your intent?

```

**Wait for user confirmation before proceeding.**

### Step 4: Update the Plan File

1. **Make focused, precise edits**:

- Use surgical changes (targeted updates) rather than wholesale rewrites.
- Maintain the existing structure unless the user explicitly requested a structural change.
- Keep all file paths and line references accurate.
- Update success criteria to reflect the new scope.

2. **Ensure consistency**:

- If adding a new phase, ensure it follows the existing formatting and level of detail.
- Update the **"What We're NOT Doing"** section if the scope has shifted.
- Maintain the distinction between **Automated** vs **Manual** success criteria.

3. **Preserve quality standards**:

- Include specific file paths for new content.
- Write measurable, binary (Pass/Fail) success criteria.

### Step 5: Sync and Review

**Present the changes made clearly**:

```text
I've updated the plan at `thoughts/plans/[filename].md`

Changes made:
- [Specific change 1]
- [Specific change 2]

The updated plan now:
- [Key improvement]
- [Another improvement]

Would you like any further adjustments?

```

---

## Important Guidelines

- **Be Skeptical**: Do not blindly accept change requests that contradict the codebase. If research shows a request is problematic, point it out.
- **Be Surgical**: Don't rewrite what isn't broken. Preserve the original author's intent where it still applies.
- **No Open Questions**: Never update a plan with "TBD" or unresolved questions. Research the answer or ask the user for clarification **before** finalization.
- **Direct Action**: You are responsible for the searching, reading, and writing. Do not wait for "sub-reports"; gather the data yourself and integrate it.

## Success Criteria Structure

When updating success criteria, always maintain this two-category structure:

1. **Automated Verification**:

- CLI commands: `make test`, `npm run lint`, `cargo check`.
- Existence of specific files or generated artifacts.

2. **Manual Verification**:

- UI/UX visual checks.
- End-to-end user flows.
- Edge cases requiring human judgment.

## Implementation Details

When updating the plan, keep the following in mind:

- **Follow SOLID and KISS** throughout implementation.

    - **SOLID**: Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation, Dependency Inversion. Example: extract one responsibility into a small class or function; depend on abstractions (interfaces) not concrete implementations.
    - **KISS**: Keep It Simple, Stupid — prefer clear, small functions over complex one-offs. Example: split a large 500-line function into smaller well-named helpers that each do one thing.

- **Code snippet policy**: include focused snippets showing only the lines that must change and any small surrounding context (preferably <= 120 lines). Do NOT paste entire files (no massive 1000+ line dumps). For larger contexts, provide file:line references and short summaries instead of full contents.

## TDD Enforcement

When updating the plan, ensure that implementation phases enforce TDD:

- **Tests First**: Any new functionality must have tests written _before_ the code.
- **Test Coverage**: Ensure the plan specifies coverage targets.
- **Failure First**: Run tests to see them fail before implementing.

## Rollback/Recovery Strategy

If the changes involve migrations, data changes, or breaking changes, include a Rollback/Recovery strategy in the plan:

- **Rollback Plan**: How to revert if things go wrong (e.g., database rollback, revert code commit).
- **Recovery Steps**: How to recover data if lost.
- **Emergency Contacts**: Who to call if things break (if applicable).
