---
description: Create handoff document for transferring work to another session
---

# Create Handoff: Universal Session Continuity

You are tasked with generating a thorough yet concise handoff document. Your goal is to "compact" the current session's state—achievements, blockers, and specific file references—so the next session can resume without losing momentum or repeating mistakes.

## 1. Filepath & Naming Convention

Create the handoff file in `thoughts/handoffs/`. Use the following naming convention:

`YYYY-MM-DD_HHMM_[TICKET-ID]_brief-description.md`

* **YYYY-MM-DD**: Today's date.
* **HHMM**: Current time (24-hour format).
* **TICKET-ID**: The project or ticket reference (e.g., `APP-456`). Use `GEN` if no specific ticket exists.
* **Description**: Kebab-case summary (e.g., `fix-auth-loop`).

---

## 2. Document Template

Structure the document with YAML frontmatter followed by structured Markdown.

```markdown
---
date: [Current ISO Timestamp]
git_commit: [Current Short Hash]
branch: [Current Branch Name]
topic: "[Task Name] Progress Summary"
status: [In Progress / Blocked / Ready for Review]
last_updated: [YYYY-MM-DD]
type: handoff
---

# Handoff: [TICKET-ID] [Brief Description]

## 🎯 Current Objectives
{What were you trying to achieve this session? Note if you were following a specific implementation plan or research doc.}

## 📍 Where We Left Off
{State exactly where the work stopped. Are you mid-refactor? Are tests passing? Mention the specific phase of work.}

## 🛠 Recent Changes
{List significant changes made. Use `file:line` syntax for precision.}
- `path/to/file.ts:45-80`: Implemented the new validator.
- `path/to/config.json`: Updated API endpoints.

## 💡 Key Learnings & "Gotchas"
{Crucial: What did you discover that isn't obvious? Mention bugs found, architectural decisions made, or patterns that MUST be followed to avoid breaking things.}

## 📂 Artifacts & References
{List the most important files for the next person to read immediately.}
- `docs/plans/feature-x.md`: The master plan.
- `src/core/logic.py`: The main file being modified.

## ⏭ Next Steps (Action Items)
{A numbered list of what the next agent should do first.}
1. Fix the failing test in `tests/auth_test.py`.
2. Connect the frontend button to the new API.
3. [ ] Task 3...

## ⚠️ Known Blockers / Notes
{Anything else? Environment issues, pending PRs, or "don't touch X because it breaks Y".}

```

---

## 3. Finalization & Instructions

1. **Be Data-Driven**: Prefer file paths and line numbers over vague descriptions.
2. **No Large Diffs**: Avoid massive code blocks. Let the next agent use `git diff` or read the referenced files.
3. **Validate Links**: Ensure all file paths mentioned actually exist.
4. **Completion**: After writing the file, provide the user with the command to resume.

### Output to User:

Once the file is written, notify the user:
"Handoff created! You can resume from this state in a new session by pointing the agent to: `path/to/handoff_file.md`."

---

## Guidelines

* **Context over Narrative**: Don't tell a story; provide a map.
* **Precise references**: Use `file:line` syntax so the next agent can jump straight to the code.
* **Assume Zero Memory**: Write as if the next agent has never seen this codebase before, but is highly technically competent.

**I am ready to generate a handoff. Should I begin summarizing our current progress now?**