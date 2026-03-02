Global Workflows
================

What this repository contains
- A curated collection of high‑quality, AI agent opinionated engineering workflows used to research, plan, implement, and iterate on code changes in large codebases. The material is written as Markdown procedures and checklists so they can be read by AI agents (specifically Google Antigravity).
- Core workflow topics include Research → Plan → Implement (RPI), SOLID analysis, PR review, creating handoffs, and CI/commit guidance.

Why this exists
- Reduce context switching: standardize how investigations, plans, and implementations are executed across projects.
- Improve handoffs: provide clear, repeatable steps for handing work between AI engineers or teams.
- Make high‑quality AI engineering work reproducible and reviewable.

Quick start
- Read the overview workflow: `create-plan.md`, `implement-plan.md`, and `iterate-plan.md`.
- If you need to generate a handoff for another AI agent engineer, see `rpi-create-handoff.md` and `resume-handoff.md`.

Repository structure
- `create-plan.md` — guide for building a practical implementation plan from research
- `research-codebase.md` — how to explore and map an unfamiliar codebase
- `implement-plan.md` — step‑by‑step instructions for implementing a plan, including verification
- `iterate-plan.md` — process for improving an implementation after initial feedback
- `test-implementation.md` — recommended approach for testing implementations

How to use these files
- Read the docs top‑to‑bottom before starting a task to internalize the intent and acceptance criteria.
- Use the command docs as playbooks during execution — they are intentionally prescriptive and designed to be copy/pasted into a terminal or issue comment.
- When creating a new workflow or updating an existing one: keep the language imperative, add examples, and include verification steps.

Contributing
- Add or improve workflows by editing existing Markdown files or adding new files under the repository root or `commands/`.
- Follow these conventions:
  - Keep content human‑readable and actionable; prefer checklists and explicit commands.
  - Use present tense, imperative voice ("Run", "Verify").
  - Include verification steps and expected outcomes.
  - Keep file names kebab‑case and descriptive (e.g., `create-plan.md`, `rpi-debug.md`).
- Open a pull request describing the change and which workflow it supports. If the change affects handoffs or team processes, tag the affected team or owner in the PR description.
