Global Workflows
================

What this repository contains
- A curated collection of high‑quality, opinionated engineering workflows and command reference documents used to research, plan, implement, and iterate on code changes. The material is written as Markdown procedures and checklists so they can be read by humans or consumed by automation.
- Core workflow topics include Research → Plan → Implement (RPI), SOLID analysis, PR review, creating handoffs, and CI/commit guidance. See the `commands/` directory for command‑style guides.

Why this exists
- Reduce context switching: standardize how investigations, plans, and implementations are executed across projects.
- Improve handoffs: provide clear, repeatable steps for handing work between engineers or teams.
- Make high‑quality engineering work reproducible and reviewable.

Quick start
- Read the overview workflow: `create-plan.md`, `implement-plan.md`, and `iterate-plan.md`.
- Follow a command template or checklist in `commands/` when performing a specific task (for example, `commands/implement_plan.md` or `commands/review_pr.md`).
- If you need to generate a handoff for another engineer, see `rpi-create-handoff.md` and `resume-handoff.md`.

Repository structure
- `create-plan.md` — guide for building a practical implementation plan from research
- `research-codebase.md` — how to explore and map an unfamiliar codebase
- `implement-plan.md` — step‑by‑step instructions for implementing a plan, including verification
- `iterate-plan.md` — process for improving an implementation after initial feedback
- `test-implementation.md` — recommended approach for testing implementations
- `commands/` — targeted command and checklist documents; examples:
  - `commands/implement_plan.md`
  - `commands/review_pr.md`
  - `commands/describe_pr.md`
  - `commands/ci_commit.md`

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

Suggested next steps
1. Skim `research-codebase.md` and `create-plan.md` to align on how this repo maps to your existing processes.
2. Pick one small workflow you perform often and adapt it into a new `commands/` checklist so it is reproducible.
3. Consider adding a short CONTRIBUTING.md and a license file if this will be shared outside your organization.

License
- This repository does not include a license file. Add `LICENSE` if you want to set reuse terms.

Contact / ownership
- If you maintain this collection, add a MAINTAINERS file or include contact information in a top‑level document.

Files referenced (examples)
- `create-plan.md`
- `implement-plan.md`
- `iterate-plan.md`
- `research-codebase.md`
- `rpi-create-handoff.md`
- `commands/review_pr.md`

If you want, I can:
1. Add a `CONTRIBUTING.md` and a default `LICENSE` for the repo (suggest MIT). (Recommended)
2. Generate a short `MAINTAINERS` file and a status badge template you can paste into the top of this README.
