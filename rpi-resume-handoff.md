---
description: Resume work from handoff document with context analysis and validation
---

# AI Resume: Direct Handoff Process

You are an AI agent resuming a project using a handoff file provided by the user. Your goal is to achieve "context parity" with the previous session before writing any code.

## Phase 1: Ingestion & Verification

As soon as the file is provided:

1. **Deep Read**: Read the handoff document in its entirety. Do not use summary tools; ingest the full text to capture nuances, specific line references, and "gotchas."
2. **Verify State**: Immediately check the codebase to ensure the "Current Status" in the handoff matches the actual files.
* *Action*: If the handoff says `feature/login` is 90% done, check the relevant files to see if they exist and contain the logic described.


3. **Cross-Reference Artifacts**: Read any specific files mentioned in the **Learnings** or **Recent Changes** sections.
* *Example*: If the handoff mentions a bug found in `utils/parser.py`, read that file to see if the fix was committed or if you need to finish it.



## Phase 2: Synthesis & Validation

Before starting work, present a summary to the user to ensure you are aligned:

> ### 📋 Handoff Analysis
> 
> 
> **Source File:** `[Filename]`
> **1. Where we left off:** > [Brief summary of the last completed milestone].
> **2. Codebase Sync:** > * [Verified] Recent changes to `[File A]` are present.
> * [Divergence] The handoff mentions `[File B]`, but it appears [missing/modified]. (Note any discrepancies here).
> 
> 
> **3. Critical Learnings:** > I have noted that [specific pattern/blocker/decision] must be respected moving forward.
> **4. Proposed Immediate Steps:**
> 1. [Task 1: e.g., Resolve the remaining TODOs in Component X]
> 2. [Task 2: e.g., Run the test suite for the new module]
> 
> 
> **Should I proceed with these steps, or would you like to adjust the priority?**

## Phase 3: Execution

Once confirmed:

* **Maintain Continuity**: Use the same naming conventions and architectural patterns identified in the handoff.
* **Update Tracking**: If the project uses a `TODO.md` or task list, update it immediately to reflect the resumed state.
* **Documentation**: Keep a mental (or scratchpad) log of new deviations from the original handoff to include in your *own* handoff at the end of this session.

## Guidelines

* **No Redundant Work**: If the handoff mentions a failed approach, **do not** attempt that approach again.
* **Context over Speed**: Spend the first few minutes reading rather than coding. A missed "Learning" in a handoff costs hours of refactoring later.
* **Assume Stale Data**: Treat the handoff as a "map" and the codebase as the "territory." If they disagree, the codebase is the truth—report the discrepancy to the user immediately.