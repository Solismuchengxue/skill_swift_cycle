# README Product-First FDE Portfolio Design

## Status

Implemented and committed on 2026-08-09. The resulting bilingual README
refresh is tracked in commit `59ffa53`; this document remains the design
record for that completed change.

## Objective

Refresh the English and Simplified Chinese READMEs so Swift Cycle presents as a credible open-source AI Skill and a strong portfolio project for an Enterprise AI / Agent Solution FDE. The README should feel polished enough for GitHub discovery while remaining lightweight, accurate, portable, and useful to real adopters.

## Audience and positioning

- Primary hiring signal: Forward Deployed Engineer work at the intersection of enterprise AI, agents, ERP/SAP, industrial data, and energy/manufacturing delivery.
- Primary product audience: developers and teams using coding agents to turn evolving requirements into verified delivery increments.
- International and Chinese readers receive equivalent product claims and structure. English remains the canonical landing page; `README.zh-CN.md` is the maintained Chinese mirror.
- Product credibility comes before personal portfolio framing. The project demonstrates FDE capability through its system design and delivery contract, not through a personal biography.

## Core message

Hero kicker:

> AI SKILL · LOOP ENGINEERING · VERIFIED DELIVERY

Hero tagline:

> From ambiguous requirements to verified AI delivery loops.

Supporting copy:

> A portable Agent Skill that turns evolving requirements into lightweight project structure, reviewable delivery increments, and evidence-backed outcomes—without importing heavyweight process.

Swift Cycle defines Loop Engineering as:

> The discipline of keeping intent, execution, evidence, and learning connected in one short, repeatable feedback loop.

The README may use the expanded product narrative:

> SCAN real state → SHAPE shared truth → SHIP the smallest reviewable increment → VERIFY with evidence → LEARN and synchronize ↻

This must be mapped back to, not replace or contradict, the canonical execution rhythm in the Skill:

> Scan quickly → make the smallest useful change → verify immediately → continue or revert.

`Loop Engineering` is Swift Cycle's product model, not an asserted industry standard.

## Visual direction

Use the approved A1 product-first, GitHub-native treatment:

- Centered hero built from maintainable README HTML.
- A small set of accurate shields for Agent Skill identity, the current release, and MIT license.
- One compact loop strip or Mermaid diagram that communicates the feedback cycle.
- Compact capability cards or a table for portability, reviewable increments, and evidence loops.
- No generated banner, custom logo, animated SVG, analytics, runtime dependency, or asset pipeline.
- Visual polish must degrade gracefully in common GitHub-compatible Markdown renderers.

The visual hierarchy should resemble a serious open-source product rather than a résumé page: clear proposition, fast comprehension, restrained badges, generous whitespace, and short sections.

## Information architecture

The English and Chinese READMEs use the same semantic order:

1. Hero and language switch.
2. The delivery problem Swift Cycle solves.
3. Loop Engineering model and its relationship to the canonical short loop.
4. AI Skill capabilities.
5. Quick Start for supported hosts.
6. What this project demonstrates / 项目体现的工程能力.
7. How the system works, including shared truth versus local execution and simple TODO versus milestone/PR queue.
8. Example delivery loops and invocation examples.
9. Compatibility, repository layout, proof boundaries, and license.

Installation remains easy to find before deep design detail. Existing valid host-specific commands and explicit-invocation boundaries must be preserved unless live verification shows they changed.

## AI Skill capability story

The README should explain four product capabilities in outcome language:

- **Project shaping:** inspect the real repository, establish the minimum project structure, and make boundaries explicit.
- **Adaptive execution:** keep simple work as a lightweight TODO; introduce a current milestone and dependency-ordered PR queue only for multi-PR or milestone work.
- **Evidence-backed delivery:** require each increment to be independently reviewable, verifiable, and reversible; continue or revert based on evidence.
- **Portable orchestration:** keep one thin, standards-aligned Skill with localized reference material and host-specific metadata, without scripts, MCP servers, or external services.

Claims must stay within repository evidence. Do not claim customer adoption, enterprise production use, autonomous operation, or broad host compatibility without proof.

## FDE portfolio signal

Place the explicit portfolio section after Quick Start so it supports rather than displaces product utility. It should show the engineering abilities demonstrated by the repository:

- **Solution shaping:** turn ambiguous requests into explicit scope, boundaries, and delivery contracts.
- **AI Skill productization:** package a working methodology as a portable, documented Agent Skill.
- **Delivery orchestration:** choose proportional process and decompose larger work into dependency-aware, reviewable increments.
- **Evidence-first execution:** connect implementation, validation, rollback, and shared-state synchronization.
- **Cross-context communication:** maintain equivalent English and Chinese product narratives for technical and business-facing audiences.

Avoid personal claims about SAP, ERP, energy, or manufacturing implementation that are not evidenced inside this repository. Those domains define the intended portfolio context, not a repository feature claim.

## System boundaries to preserve

- The tracked feasibility report, `docs/roadmap.md`, or GitHub Issues remain the long-lived shared truth.
- Local ignored `TODO.md` remains the current execution view and must not be described as the sole long-term plan.
- Ordinary tasks keep a normal TODO list; milestone/PR structure is conditional rather than mandatory.
- Each PR-sized increment carries its ID, milestone, deliverable, scope, dependencies, verification, status, and PR link.
- The Skill remains explicitly invoked and does not imply autonomous background execution.
- Swift Cycle does not depend on or reproduce Superpowers mechanisms. The design-work artifact path under `docs/superpowers/specs/` records the design process only and is not a runtime dependency or product claim.

## Bilingual maintenance contract

- `README.md` and `README.zh-CN.md` must match in section order, capability coverage, installation behavior, compatibility statements, and constraints.
- Translation should be natural rather than literal. Keep standard terms such as Agent Skill, Loop Engineering, FDE, PR, and TODO recognizable where that improves cross-language search and comprehension.
- English marketing copy may be tighter; Chinese copy should preserve the same meaning and evidence level.

## Verification and acceptance

Before completion:

- Compare both READMEs for semantic parity.
- Confirm every badge, internal anchor, relative file link, and external documentation link resolves.
- Confirm the Loop Engineering narrative does not contradict the canonical `SKILL.md` behavior.
- Run the repository's OpenAI Skill `quick_validate` command.
- Run `gh skill publish --dry-run` if the repository's existing workflow supports it.
- Run Markdown link checks using existing repository tooling; do not install new dependencies for this change.
- Run `git diff --check`, inspect the final diff, and confirm the affected-file set is limited to the approved README refresh and its necessary design/maintenance records.
- Record actual progress and evidence in ignored `TODO.md` and `DEVLOG.md`; do not mark unverified checks complete.

## Non-goals

- No change to canonical Skill behavior, release version, package contents, or user-level installed Skill.
- No new governance framework, build system, package dependency, hosted site, telemetry, or external service.
- No release, commit, push, or installation without separate explicit authorization.
