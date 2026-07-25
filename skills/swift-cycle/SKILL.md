---
name: swift-cycle
description: Manual-invocation workflow for lightweight governance of personal and small software projects. Use only when the user explicitly invokes swift-cycle to initialize or review README, DESIGN, AGENTS, local TODO and DEVLOG, shared docs, candidate evaluations, ADR decisions, documentation drift, or project closeout. Keep small local changes fast and avoid heavyweight process.
license: MIT
---

# Swift Cycle

## Goal

Maintain design consistency, execution continuity, and traceability with the smallest useful documentation set. Adjust the framework incrementally from repository evidence. Never describe a candidate, test, tool, or decision as verified when evidence is missing.

## Use the project's language

1. Respond and create documents in the user's requested language.
2. Preserve terminology and filename conventions already established in the repository.
3. Keep standard filenames such as `README.md`, `DESIGN.md`, `AGENTS.md`, `TODO.md`, and `DEVLOG.md` unchanged unless the project already uses an equivalent.
4. For Simplified Chinese terminology and document wording, read `references/zh-CN.md`.

## Inspect the real state first

1. Read repository instructions, `README.md`, `DESIGN.md`, relevant `docs/`, `.gitignore`, and existing maintenance records.
2. Inspect the Git branch, status, and relevant diff. Separate pre-existing user changes from the current task.
3. Distinguish confirmed facts, assumptions, and inferences. Do not invent repository structure, tests, tools, decisions, or validation results.
4. Preserve existing user work. Do not remove data, discard changes, or perform unrelated cleanup.

## Reuse before building

Before implementation:

1. Check the current repository for reusable code, scripts, dependencies, tools, documentation, and implementation patterns.
2. Then evaluate official solutions and already installed Skills, plugins, MCP integrations, or development tools.
3. If those are insufficient, evaluate maintained third-party tools and mature open-source projects.
4. Summarize fit, limits, integration cost, major risks, and availability.
5. Obtain user confirmation before installing, enabling, downloading, connecting, or configuring a new external solution.

Do not perform unbounded research for a simple, local change with an obvious implementation.

## Match governance to task size

- **Project initialization or governance calibration:** establish or reconcile the complete core framework.
- **Architecture, tool responsibility, or data-boundary change:** update the design entry point and affected shared documentation.
- **Candidate solution or controlled trial:** use the candidate lifecycle and a status-marked evaluation.
- **Small, local, explicit change:** inspect, change minimally, and verify; do not add an RFC, ADR, design document, or implementation plan.
- **Project closeout:** reconcile documentation, remove stale states safely, and extract methodology from real work.

## Establish the core framework

At project start, establish these responsibilities. Reuse equivalent existing files instead of maintaining duplicates.

### `README.md`

- Keep a user-only perspective.
- Include the project introduction, installation or startup, usage, and user-visible limitations.
- Commit it to Git.
- Exclude internal decisions, maintenance evidence, agent notes, and short-term tasks.

### `DESIGN.md`

- Use it as the concise design entry point.
- Record goals, principles, system shape, key boundaries, adopted architecture, and links to detailed documents.
- Mark candidates clearly and keep them separate from adopted architecture.
- Commit it to Git and avoid copying long details from `docs/`.

### `AGENTS.md`

- Record project rules, safety boundaries, documentation sync triggers, and verification requirements.
- Keep different agents and sessions aligned.
- Commit it to Git.

### `DEVLOG.md`

- Record failures, rejected approaches, internal judgments, maintenance evidence, and evolution history.
- Keep it local at the repository root and ignore it in Git.

### `TODO.md`

- Record current actions, priorities, blockers, and next steps.
- Keep entries short, executable, and current.
- Keep it local at the repository root and ignore it in Git.
- Do not use it as the only store for cross-machine or long-term commitments.

### `docs/`

- Store long-lived shared requirements, architecture, runbooks, roadmaps, evaluations, and ADRs.
- Commit it to Git and index detailed documents from `DESIGN.md`.
- If no detailed document exists yet, create a meaningful status-bearing entry so the directory is not an empty placeholder.

## Initialize honest drafts

Except for the user-facing `README.md`, an initial document may be marked `planned` or `draft`, but it must not be blank. Record:

- purpose;
- status;
- current conclusion;
- open questions;
- update trigger.

Keep internal draft state out of `README.md`. Put it in `DESIGN.md`, `TODO.md`, or relevant shared documentation.

Treat `METHODOLOGY.md` as an explicit exception: create it only near project closeout from evidence of real work, and keep it local and ignored unless the user chooses otherwise.

## Manage plans and candidates

### Long-term plans

- Store cross-machine, cross-session commitments in `docs/roadmap.md` or the project's shared issue tracker.
- A roadmap may begin as a status-marked draft, but do not describe planned work as completed.
- Keep local `TODO.md` focused on immediate actions and blockers.

### Candidate lifecycle

Follow this order:

1. Mark the idea as a candidate in `DESIGN.md` and define its boundary.
2. Schedule a controlled trial in local `TODO.md`.
3. Create a status-marked evaluation document when the planned evaluation needs durable shared context.
4. When the trial starts, mark it in progress and collect evidence.
5. After validation, record acceptance or rejection in an ADR when the decision is long-lived and significant.
6. Update the adopted design only after the decision is supported.

An evaluation should cover:

- purpose and status;
- goals and non-goals;
- risks;
- acceptance and rejection criteria;
- current evidence;
- rollback path;
- open questions and update trigger.

Do not list a candidate tool as an adopted dependency before validation. Preserve important rejected or replaced decisions instead of deleting their rationale.

## Synchronize on real triggers

- Architecture, tool responsibility, or data boundary changes: update `DESIGN.md` and affected shared docs.
- Experiment, blocker, or next-action changes: update local `TODO.md`.
- Failure, rejected attempt, maintenance evidence, or important internal judgment: update local `DEVLOG.md`.
- Long-lived and significant formal decision: complete an ADR after validation.
- User-visible behavior, installation, or usage changes: update `README.md`.

## Run the short loop

Repeat:

1. Scan the relevant state and risk.
2. Make the smallest change that advances the current goal.
3. Run the smallest relevant verification immediately.
4. Continue when evidence supports the change; otherwise diagnose and correct or revert the current step.
5. Do not expand scope merely because governance work exposed unrelated opportunities.

## Verify before completion

Scale verification to the task and at minimum:

1. Review the final diff and confirm every changed file belongs to the request.
2. Run `git diff --check`.
3. Check Markdown links when entry points or paths change.
4. Run `git check-ignore` when local-file rules change.
5. Confirm local maintenance files are neither tracked nor staged.
6. Report any check not run, why it was skipped, and what remains unverified.

Claim completion only after verification.

## Report concisely

Report:

- what changed;
- why the current layering was chosen;
- checks actually run and their results;
- shared files still uncommitted;
- files kept local;
- unresolved candidates, risks, or open questions.
